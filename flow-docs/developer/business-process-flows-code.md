---
title: Kod kullanarak iş süreci akışlarıyla çalışma | MicrosoftDocs
description: Daha verimli ve kolaylaştırılmış iş süreçlerini oluşturmak için iş süreci akışlarıyla programlı olarak nasıl çalışacağınızı öğrenin.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 5ce11084cb9a430899fd0a4b672e009c0dc22d25
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547742"
---
# <a name="work-with-business-process-flows-using-code"></a>Kod kullanarak iş süreci akışlarıyla çalışma
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

*İş süreci akışı* , daha verimli ve kolaylaştırılmış satış, hizmet ve diğer iş süreçlerini oluşturmanızı sağlar. Varlık formlarının üst kısmına özel denetimler yerleştirerek iş sürecinizin bir görselleştirmesi oluşturur. Kullanıcılar, çeşitli satış, pazarlama veya hizmet işlemlerinin tamamlama aşamasına göre yapılır. Her işlem birden çok aşama ve adımı destekler. Adımları ekleyebilir veya kaldırabilir, aşamaların sırasını değiştirebilir veya iş süreci akışına yeni varlıklar ekleyebilirsiniz.  
  
Farklı iş süreci akış örnekleri aynı varlık kaydında aynı anda çalışabilir. Kullanıcılar eşzamanlı iş süreci örnekleri arasında geçiş yapabilir ve işleri işlemdeki geçerli bir aşamada sürdürür. 

Bu konuda iş süreci akışlarıyla programlama yoluyla nasıl çalışabilmeniz hakkında bilgi verilmektedir.

> [!NOTE]
> İş süreci akışlarıyla çalışmak için kod yazmanız gerekmez. İş süreci akışları oluşturmak ve yönetmek için Kullanıcı arabirimini kullanma hakkında bilgi için bkz. [Iş süreci akışlarına genel bakış](../business-process-flows-overview.md)  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>İş işlem akışı önkoşulları 

Kullanıcı arabirimi formlarını güncelleştiren özel varlıklar ve varlıklar iş süreci akışına katılabilir. Güncelleştirilmiş Kullanıcı arabirimi varlıklarının <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> özelliği `true`olarak ayarlanmıştır. 

İş süreci akışı için bir varlığı etkinleştirmek üzere <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> özelliğini `true`olarak ayarlayın.

> [!IMPORTANT]
>  İş süreci akışı için bir varlığın etkinleştirilmesi tek yönlü bir işlemdir. Geri alamazsınız.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>İş süreci akışını tanımlama
  
İş süreci akışını tanımlamak için Visual Business Process Flow tasarımcısını kullanın. Daha fazla bilgi: [iş süreci akışı oluşturma](../create-business-process-flow.md)

Varsayılan olarak, `Draft` durumunda bir iş süreci akış kaydı oluşturulur.  

Bir iş süreci akış tanımı <xref:Microsoft.Dynamics.CRM.workflow> varlığında depolanır ve iş süreci akışı için aşama bilgileri <xref:Microsoft.Dynamics.CRM.processstage> varlığında depolanır.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>İş süreci akışını etkinleştir  
 İşlem akışını kullanabilmeniz için etkinleştirmeniz gerekir. Etkinleştirmek için, `Workflow` varlık için `prvActivateBusinessProcessFlow` ayrıcalığına sahip olmanız gerekir. `Workflow` varlık kaydının durumunu `Activated`olarak ayarlamak için <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> iletisini kullanın. Daha fazla bilgi: [güncelleştirme kullanarak özel Işlemler gerçekleştirme](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > İş süreci akışını etkinleştirmek için iş süreci akış tasarımcısını da kullanabilirsiniz. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>İş süreci akış varlığı 
 Karşılık gelen `Workflow` varlık kaydının durumunu değiştirerek veya iş süreci akış tasarımcısını kullanarak bir iş süreci akış tanımını etkinleştirdikten sonra, etkinleştirilen işi depolamak için aşağıdaki ada sahip bir özel varlık otomatik olarak oluşturulur işlem akışı örnekleri: " *\<activesolutionprefix >* _ *\<UniqueName >* ", burada UniqueName, belirttiğiniz adından türetilir.  
  
 Örneğin, iş süreci akış tanımının adı olarak "My Custom BPF" belirttiyseniz ve etkin çözümünüz için varsayılan yayımcıyı (yeni) kullanıyorsanız, işlem örneklerinin depolanması için oluşturulan özel varlığın adı "new_mycustombpf" olacaktır.  
  
 `uniquename` değeri bir iş işlemi akış tanımı için kullanılabilir değilse, örneğin iş süreci akışı önceki bir sürümden çözümün parçası olarak içeri aktarıldıysa, özel varlığın varsayılan adı "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`" olacaktır:  
  
> [!IMPORTANT]
>  Örnek iş süreci akışı kayıtları, ilgili iş süreci akış örneği kayıtlarını depolamak için sistem varlıklarını kullanır.  
>   
>  Ancak, oluşturduğunuz tüm yeni iş süreci akış tanımları, daha önce açıklandığı gibi örnek kayıtlarını depolamak için özel varlıklar kullanır. 

Aşağıdaki yollarla iş süreci akışı varlığınızın adını alabilirsiniz:

- **Kullanıcı arabirimini kullanma**: iş süreci akışı varlığınıza gitmek için özelleştirme Kullanıcı arabirimini kullanın:

    ![](media/bpf-entity-name.png)
- **Web API 'Sini kullanarak**: aşağıdaki isteği kullanın:

    **İsteyen**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Yanıtıyla**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }
    ```
- **Kuruluş hizmetini kullanarak**: Aşağıdaki kod örneğini kullanın:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 
    ```
> [!NOTE]
> <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> özelliği, iş süreci akış varlıkları için `true`. Aşağıdaki Web API isteğini çalıştırarak, örneğiniz içindeki tüm iş işlem akışı varlıklarını alabilirsiniz:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>İş işlem akışları için güvenliği yönetme

İş süreci akış örneklerinin depolanması için bir iş süreci akışını etkinleştirmek üzere otomatik olarak oluşturulan özel varlık, Common Data Service ' deki diğer tüm özel varlıklar için standart güvenlik modeline uyar. Bu, bu varlıklarda verilen ayrıcalıkların iş için Kullanıcı işlem akışları için çalışma zamanı izinlerini tanımladığını gösterir.

Özel iş süreci akış varlığı kuruluş kapsamına sahiptir. Bu varlıktaki normal oluşturma, alma, güncelleştirme ve silme ayrıcalıkları, kullanıcıların kendilerine atanan rollerine göre sahip olacağı izni tanımlar. Varsayılan olarak, iş süreci akışı özel varlığı oluşturulduğunda, yalnızca **Sistem Yöneticisi** ve **Sistem Özelleştirici** güvenlik rollerine erişim verilir ve yeni iş süreci akışı varlığına (için) açıkça izin vermeniz gerekir. Örneğin, **özel BPF**), diğer güvenlik rolleri için gereken şekilde.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>İş süreci akışı varlık kayıtlarını oluşturma, alma, güncelleştirme ve silme (işlem örnekleri)  
 Bir iş işlemi akış tanımını etkinleştirmede otomatik olarak oluşturulan özel varlık, iş süreci akış tanımı için tüm işlem örneklerini depolar. Özel varlık, Web API 'SI ve CRM 2011 uç noktası kullanılarak kayıtların standart programsal olarak oluşturulmasını ve yönetimini (işlem örnekleri) destekler.

> [!IMPORTANT]
> Bir varlık kaydı için başka bir işlem örneğine geçiş yapmak yalnızca kullanıcı arabirimi (istemci) veya bu bölümde bulunan bilgiler kullanılarak programlı bir şekilde desteklenir. Artık `SetProcess` iletisini (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> veya <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>), hedef varlık kaydı için programlı olarak işlemleri değiştirmek (etkin işlem örneği olarak başka bir iş işlem akışı ayarlamak) için kullanamazsınız. 

 3 aşamada "My Custom BPF" adlı bir varlık arası iş süreci akışımız olan aşağıdaki örneği göz önünde bulundurun: S1: Account, S2: Account ve S3: Contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Bir iş süreci akış varlığının tüm kayıtlarını (örneklerini) alma
 İş süreci akışı varlığınızın adı "new_mycustombpf" ise, iş süreci akışı varlığınızın tüm kayıtlarını (işlem örnekleri) almak için aşağıdaki sorguyu kullanın:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

Bu noktada, herhangi bir örnek yok olduğu için yanıtınıza herhangi bir örnek alınamaz. Bu konunun ilerleyen kısımlarında iş süreci akış tanımınızın bir örneğini oluşturduktan sonra bu isteği çalıştırın.

> [!NOTE]
> İş süreci akışı varlığınızın adını nasıl alacağınızı öğrenmek için önceki bölüm olan [iş süreci akışı varlığına](#business-process-flow-entity)bakın.
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>İş süreci akışı varlık kaydı oluşturma (işlem örneği) 

Kullanıcı arabirimini kullanmadan bir varlık kaydı için başka bir iş işlem akışına geçiş yapmak istiyorsanız, programlı olarak bir iş süreci akışı varlık kaydı (işlem örneği) oluşturun. 

Bir iş süreci akışı varlık kaydı oluşturmak için aşağıdaki değerleri belirtmeniz gerekir: 
- `@odata.bind` ek açıklamasını kullanarak, tek değerli gezinti özelliğini ayarlayarak, iş süreci akışı varlık kaydını bir birincil varlık kaydıyla ilişkilendirin. İş süreci akış tanımınızın birincil varlık kaydına işaret eden gezinti özelliği adını bulmak için, [CSDL $Metadata belgesini](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document)kullanın. 
- `@odata.bind` ek açıklamasını kullanarak tek değerli gezinti özelliğini ayarlayarak iş süreci akışı varlık kaydını iş süreci akış tanımında belirtilen geçerli bir aşamaya ilişkilendirin. İş süreci akış tanımınızın aşama kaydına işaret eden gezinti özelliği adını (genellikle `activestageid`) bulmak için, [CSDL $Metadata belgesini](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document)kullanın.

    Ayrıca, iş süreci akış tanımınızın KIMLIĞININ 2669927e-8ad6-4f95-8a9a-f1008af6956f olduğunu varsayarak aşağıdaki Web API isteğini kullanarak bir iş süreci akış tanımına ait tüm aşamalar hakkında bilgi alabilirsiniz:

    **İsteyen**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Yanıtıyla**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

Ardından, bir hesap kaydı için iş süreci akış tanımınızın bir örneğini oluşturmak için aşağıdaki isteği kullanın, S1 (ID = a176be9e-9a68-E711-80e7-00155d41e206) ve işlem örneğinin ilk aşaması olarak ayarlanan etkin aşamada 9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**İsteyen**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**Yanıtıyla**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Etkin aşama kümesi olan iş süreci akış tanımınızın bir örneğini ilk ***aşama dışında bir aşama olarak*** oluşturmak isterseniz, isteğinize `traversedpath` de sağlamanız gerekir. Yol içine geçilen işlem, iş süreci akış örneğinin ziyaret edilen aşamalarını temsil eden, işlem aşaması kimliklerinin virgülle ayrılmış dizesidir. Aşağıdaki istek, bir hesap kaydı (ID = 679b2464-71b5-E711-80f5-00155d513100) için bir örnek oluşturur ve ikinci aşama olarak bir etkin aşama kümesi, S2 (ID = 19a11fc0-3398-4214-8522-cb2a97f66e4b).

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>İş süreci akışı varlık kaydını güncelleştirme (işlem örneği)

Bir işlem örneğini bir sonraki veya önceki aşamaya geçmek, bir işlem örneğini bırakmak, bir işlem örneğini yeniden etkinleştirmek veya bir işlem örneğini işlemek için güncelleyebilirsiniz. 

#### <a name="stage-navigation"></a>Aşama gezintisi

Farklı bir aşamaya gitmek için, bir işlem örneği kaydını, etkin aşama KIMLIĞINI değiştirmek ve geçiş yolunu uygun şekilde güncelleştirmek için güncelleştirmeniz gerekir. Bir iş süreci akış örneğini güncelleştirirken yalnızca bir sonraki veya önceki aşamaya geçmeniz gerektiğini unutmayın.

Aşama gezintisi gerçekleştirmek için, güncelleştirmek istediğiniz iş süreci akışı örneğinin KIMLIĞI gerekir. İş süreci akışınızın tüm örneklerini almak için, bkz. [bir iş süreci akış varlığının tüm kayıtlarını alma (örnekler)](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) daha önce.

Güncelleştirmek istediğiniz işlem örneğinin KIMLIĞI dc2ab599-306d-e811-80ff-00155d513100 olduğunu varsayarsak, etkin aşamayı S1 'ten S2 'ye güncelleştirmek için aşağıdaki isteği kullanın:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>İşlem örneğinin durumunu değiştirme: durdurma, yeniden etkinleştirme veya bitiş 

Bir işlem örneği şu durumlardan birine sahip olabilir: **etkin**, **tamamlandı**veya **durduruldu**. Durum, işlem örneği kaydındaki aşağıdaki özniteliklere göre belirlenir:

- **StateCode**: işlem örneğinin durumunu görüntüler.

    |deeri|etiketin|
    |-----|-----|
    |0    |Bkz|
    |1    |Olmadan|

- **StatusCode**: işlem örneğinin durumu hakkındaki bilgileri görüntüler.

    |deeri|etiketin|
    |-----|-----|
    |1    |Bkz|
    |iki    |Bitirdikten|
    |03    |Kesilmiş|

Bu nedenle, bir işlem örneğini **durdurmak** için aşağıdaki isteği kullanın `statecode` ve `statuscode` değerlerini uygun şekilde ayarlayın:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> Herhangi bir aşamada bir işlem örneğini iptal edebilirsiniz.

Benzer şekilde, bir işlem örneğini yeniden etkinleştirmek için yukarıdaki koddaki `statecode` ve `statuscode` değerlerini sırasıyla **0** ve **1** ile değiştirin.

Son olarak, işlem örneğinin durumunu **tamamlandı**olarak ayarlamak için, yalnızca bir işlem örneğinin son aşamasında olabilecek, yukarıdaki koddaki `statecode` ve `statuscode` değerlerini sırasıyla **0** ve **2** ile değiştirin.

#### <a name="cross-entity-navigation"></a>Çapraz varlık gezintisi

Bu örnekteki çapraz varlık gezintisi için, işlem örneğinin etkin aşamasını son aşama, S3 (ID = a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a) olarak ayarlamanız, geçiş yolunu uygun şekilde güncelleştirmeniz ve bir kişi kaydını birincil varlık kaydı olarak bu şekilde ayarlamanız gerekir iş süreci akış tanımı.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>İş süreci akışı varlık kaydını silme (işlem örneği)

Aşağıdaki Web API isteğini kullanın:

**İsteyen**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Yanıtıyla**

Kayıt varsa, silme işleminin başarılı olduğunu belirtmek için durum 204 olan normal bir yanıt alırsınız. Varlık bulunmazsa 404 durumuna sahip bir yanıt alırsınız.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Retrieveprocessınstances ve RetrieveActivePath iletilerini kullanma

Tüm iş süreci tanımlarında bir varlık kaydı için tüm iş işlem akışı örneklerini almak üzere `RetrieveProcessInstances` iletisini (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> veya <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) kullanın. Bir varlık için döndürülen iş süreci akış örnekleri, örneğin `modifiedon` özniteliğine göre sıralanır. Örneğin, en son değiştirilen iş süreci akış örneği, döndürülen koleksiyondaki *ilk* kayıt olacaktır. En son değiştirilen iş süreci akış örneği, bir varlık kaydı için Kullanıcı arabiriminde etkin olan bir işlemdir.  
  
`RetrieveProcessInstances` iletisinin kullanılması sonucunda bir varlık kaydı için döndürülen her iş süreci akış örneği kaydı, etkin aşamanın KIMLIĞINI, etkin aşamayı bulmak için kullanılabilecek `processstageid` özniteliğinde depolar ve ardından önceki veya sonraki aşamaya geçer. Bunu yapmak için, önce bir iş süreci akış örneğinin etkin yolunu ve işlem akışı örneğinde bulunan aşamaları `RetrieveActivePath` iletisini kullanarak bulmanız gerekir (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> veya <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Bir iş işlemi akış örneği için etkin aşamasına ve etkin yol bilgilerine sahip olduktan sonra, etkin yoldaki önceki veya sonraki aşamaya geçmek için bu bilgileri kullanabilirsiniz. Aşamaların ileri gezinmesinin sırayla yapılması gerekir, diğer bir deyişle, yalnızca etkin yoldaki bir sonraki aşamaya geçmeniz gerekir.   
  
 Kodun, bu iki yöntemin kullanımını ve [kuruluş hizmetini](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)kullanarak aşama gezinmesini gösterdiği tüm örnek için bkz. [örnek: Iş süreci akışlarıyla çalışma](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Varlık kaydı oluştururken iş süreci akışını uygulama

Bu bölümde, iş süreci akışlarını Common Data Service ' de oluşturulan yeni varlık kayıtlarına otomatik olarak uygulamak için varsayılan davranış ve yeni varlık kayıtları için tercih ettiğiniz iş süreci akışını uygulamak üzere nasıl geçersiz kılabileceğiniz hakkında bilgi verilmektedir.

Varsayılan olarak, için birden çok iş süreci akışı tanımlanmış bir varlık için, sistem aşağıdaki çok adımlı mantığı kullanarak yeni varlık kaydına bir iş süreci akışı uygular:
1. İş süreci akış tanımı kayıtlarının **Iş akışı.** sın yenisliği özniteliğini temel alarak yeni varlık kaydı için geçerli olan tüm iş süreci akışlarını belirler.
2. Geçerli kullanıcının erişimi olan iş süreci akış tanımlarını tanımlama. Bir iş süreci akışına erişimin nasıl belirlendiği ve yönetildiği hakkında bilgi için, bu konunun önceki kısımlarında yer alarak [iş için güvenlik işlem akışlarını yönetme](#BPFSecurity) bölümüne bakın.<br/>  
3. Sistemdeki tüm iş süreci akış tanımları, varlık başına küresel bir sıraya tabidir. İş süreci akışının sırası **Iş akışı. ProcessOrder** özniteliğinde saklanır. Bir varlık için iş süreci akış tanımları bu sıraya göre sıralanır ve en az sipariş değerine sahip olan değer çekilir.
4. Son olarak, bir iş uygulamasından (uygulama modülü) varlık kaydı oluşturulduysa, yeni varlık kaydına otomatik olarak uygulanacak iş süreci akışını seçmek için bir veya daha fazla filtreleme düzeyi uygulanır. Kullanıcılar, bir uygulamada çalışırken, yalnızca ilgili varlıklara, iş süreci akışlarına, görünümlere ve formlarına, iş uygulamasına atanmış güvenlik rollerinin sanallarından erişimi olan formlara erişebilirler. 
    - İş uygulaması herhangi bir iş süreci akışı içermiyorsa, iş süreci akışı 3. adım kadar açıklandığı şekilde uygulanır.
    - İş uygulamasında bir veya daha fazla iş işlemi akışı varsa, yalnızca uygulamada bulunan iş süreci akışları uygulanabilir. Bu durumda, Kullanıcı bir iş uygulaması bağlamında çalışırken, adım 3 ' ten iş süreci akışları, uygulama modülünde bulunan iş uygulamasının bir parçası olan ve işlem sırasına göre sıralanmış olan iş kolu listesine göre filtrelenmiştir. 
    - Varlık için bir iş uygulaması akışı yoksa veya kullanıcının erişimi olan bir iş süreci yoksa, yeni varlık kaydı için hiçbir iş süreci akışı uygulanmaz.

Yeni varlık kayıtlarına otomatik olarak uygulanan iş süreci akışlarının varsayılan mantığını geçersiz kılabilirsiniz. Bunu yapmak için, yeni bir varlık kaydı oluştururken varlığın **ProcessId** özniteliğini aşağıdaki değerlerden birine ayarlayın:
- Yeni varlık kayıtları için bir iş süreci akışını ayarlamayı atlamak için **Guid. Empty** olarak ayarlayın. Varlık kayıtlarını toplu olarak oluşturuyorsanız ancak iş süreci akışının bunlara uygulanmasını istemiyorsanız bunu yapmak isteyebilirsiniz.
- Belirli bir iş süreci akışı varlığına (bir varlık başvurusu olarak) ayarlayın. Bu durumda, sistem varsayılan mantık yerine belirtilen iş süreci akışını uygular.

Yeni bir varlık kaydı oluştururken **ProcessId** özniteliği için bir değer ayarlanmamışsa, sistem, daha önce açıklandığı gibi varsayılan mantığı uygular.

> [!NOTE]
> Yeni varlık kayıtlarına otomatik olarak uygulanan iş süreci akışlarının varsayılan mantığını geçersiz kılmak yalnızca program aracılığıyla desteklenir. Bunu Kullanıcı arabirimini kullanarak yapamezsiniz.

## <a name="legacy-process-related-attributes-in-entities"></a>Varlıklarda işle ilgili eski öznitelikler

İş süreci akışları için etkinleştirilen varlıklarda işle ilgili eski öznitelikler ( **ProcessId**, **Yüklemekimliği**ve **TraversedPath**gibi) zaten kullanım dışıdır. Hedef varlık kayıtları için bu eski işlemle ilgili öznitelikleri işlemek, iş süreci akış durumunun tutarlılığını garanti etmez ve desteklenen bir senaryo ***değildir*** . Önerilen yol, iş süreci akışı varlık [kayıtlarını oluşturma, alma, güncelleştirme ve silme](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances) bölümünde açıklandığı gibi iş süreci akış varlığının özniteliklerini kullanmaktır (işlem örnekleri)

Bunun tek istisnası, önceki bölümde açıklandığı gibi iş süreci akışının varsayılan uygulamasını yeni kayda geçersiz kılmak üzere bir varlık kaydı oluştururken program aracılığıyla **ProcessId** özniteliğini program aracılığıyla değiştiriyor: [iş Uygula bir varlık kaydı oluşturulurken işlem akışı](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>İş süreci akışları için istemci tarafı programlama desteği  
 Form betiklerinizde iş süreci akışlarıyla etkileşim kurmak için kullanabileceğiniz bir istemci tarafı nesnesi vardır. İş süreci akışları bir işleme her uygulandığında istemci tarafı olaylarını tetikler, aşama değişir veya durum `Active`, `Finished`veya `Aborted`olarak değişir. Daha fazla bilgi: [FormContext. Data. Process (ISTEMCI API Başvurusu)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>En fazla işlem, aşama ve adım sayısı  
 Varlık başına, en fazla etkinleştirilen iş işlemi akışı sayısı için varsayılan değer 10 ' dur. `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity` özniteliğini kullanarak farklı bir değer belirtebilirsiniz. Ancak değer 10 ' dan büyükse, işlemleri değiştirdiğinizde sisteminizin performansında bir azalma veya atanan iş süreci akışına sahip bir kayıt açarsınız. Bu, özellikle birden çok varlık yayılane olursa fark edilebilir.  
  
 Aşağıdaki ayarlar özelleştirilemez:  
  
-   İşlemdeki varlık başına en fazla aşama sayısı 30 ' dur.  
  
-   Her bir aşamadaki en yüksek adım sayısı 30 ' dur.  
  
-   İşlem akışına katılabileceğiniz en fazla varlık sayısı 5 ' tir.  

