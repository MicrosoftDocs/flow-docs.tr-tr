---
title: Kod kullanarak iş süreci akışları ile çalışma | MicrosoftDocs
description: İş süreci akışlarıyla program aracılığıyla çalışıp daha verimli ve sorunsuz iş süreçleri oluşturmayı öğrenin.
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
ms.openlocfilehash: ae3633047bda556058c8e2ec94e6411e7f277e76
ms.sourcegitcommit: 50ea1cdd763863a2cbc88f9f965bdf9351f1059c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/28/2018
ms.locfileid: "44691078"
---
# <a name="work-with-business-process-flows-using-code"></a>Kod kullanarak iş süreci akışları ile çalışma

*İş süreci akışı* daha verimli ve sorunsuz bir satış süreci, hizmet süreci ve başka iş süreçleri oluşturmanıza olanak tanır. Varlık formlarının üst kısmına özel denetimler yerleştirerek iş sürecinizin görselleştirmesini oluşturur. Kullanıcılara satış, pazarlama veya hizmet süreçlerinin çeşitli aşamalarından tamamlanma aşamasına kadar yol gösterilir. Her süreç çeşitli aşamaları ve adımları destekler. Adımları ekleyip kaldırabilir, aşamaların sırasını değiştirebilir veya iş süreci akışına yeni varlıklar ekleyebilirsiniz.  
  
Aynı varlık kaydında farklı iş süreci akış örnekleri eş zamanlı olarak çalıştırılabilir. Kullanıcılar eş zamanlı iş süreci örnekleri arasında geçiş yapabilir ve sürecin geçerli aşamasındaki çalışmalarını sürdürebilir. 

Bu konuda, iş süreci akışlarıyla program aracılığıyla nasıl çalışabileceğiniz hakkında bilgi sağlanır.

> [!NOTE]
> İş süreci akışlarıyla çalışmak için kod yazmanız gerekmez. Kullanıcı arabirimini kullanarak iş süreci akışlarını oluşturma ve yönetme hakkında bilgi için bkz. [İş Süreci Akışlarına genel bakış](../business-process-flows-overview.md)  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>İş süreci akışı için önkoşullar 

Özel varlıklar ve güncelleştirilmiş kullanıcı arabirimi formları olan varlıklar iş süreci akışına katılabilir. Güncelleştirilmiş kullanıcı arabirimi varlıklarının <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> özelliği `true` olarak ayarlanmıştır. 

İş süreci akışında varlığı etkinleştirmek için <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> özelliği `true` olarak ayarlayın.

> [!IMPORTANT]
>  İş süreci akışı için varlığı etkinleştirmek tek yönlü bir işlemdir. Geri alamazsınız.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>İş süreci akışını tanımlama
  
İş süreci akışı tanımlamak için görsel iş süreci akışı tasarımcısını kullanın. Daha fazla bilgi: [İş süreci akışı oluşturma](../create-business-process-flow.md)

Varsayılan olarak, iş süreci akış kaydı `Draft` durumunda oluşturulur.  

İş süreci akışı tanımı <xref:Microsoft.Dynamics.CRM.workflow> varlığında depolanır ve iş süreci akışı için aşama bilgileri de <xref:Microsoft.Dynamics.CRM.processstage> varlığında depolanır.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>İş süreci akışını etkinleştirme  
 İş sürecini kullanabilmeniz için önce etkinleştirmelisiniz. Etkinleştirmek için `Workflow` varlığı üzerinde `prvActivateBusinessProcessFlow` ayrıcalığınızın olması gerekir. `Workflow` varlık kaydının durumunu `Activated` olarak ayarlamak için <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> iletisini kullanın. Daha fazla bilgi: [Güncelleştirme kullanarak özel işlemler gerçekleştirme](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > İş süreci akışı tasarımcısını kullanarak da iş süreci akışını etkinleştirebilirsiniz. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>İş süreci akışı varlığı 
 İlgili `Workflow` varlığı kaydının durumunu değiştirerek veya iş süreci akışı tasarımcısını kullanarak iş süreci akışı tanımını etkinleştirdikten sonra, etkinleştirilmiş iş süreci akışı örneklerini depolamak üzere şu adda özel bir varlık otomatik olarak oluşturulur: "*\<activesolutionprefix>*_*\<uniquename>*"; burada uniquename, sizin belirttiğiniz addan türetilir.  
  
 Örneğin, iş süreci akışı tanımının adı olarak "My Custom BPF" belirttiyseniz ve yeni etkin çözümünüz için varsayılan yayımcıyı (new) kullanıyorsanız, süreç örneklerini depolamak için oluşturulan özel varlığın adı "new_mycustombpf" olacaktır.  
  
 İş süreci akışı tanımı için `uniquename` değeri yoksa, örneğin iş süreci akışı önceki sürümden bir çözümün parçası olarak içeri aktarıldıysa, özel varlığın varsayılan adı "*\<activesolutionprefix>*\_bpf\_*<GUID_BPF_Definition>* olur:  
  
> [!IMPORTANT]
>  Örnek iş süreci akışı kayıtları, ilgili iş süreci akışı örneği kayıtlarını depolamak için sistem varlıklarını kullanır.  
>   
>  Öte yandan, oluşturduğunuz tüm yeni iş süreci akışı tanımları daha önce açıklandığı gibi örnek kayıtlarını depolamak için özel varlıkları kullanır. 

İş süreci akışı varlığınızın adını almak için aşağıdaki yollardan birini kullanabilirsiniz:

- **Kullanıcı arabirimini kullanma**: Özelleştirme kullanıcı arabirimini kullanarak iş süreci akışı varlığınıza göz atın:

    ![](media/bpf-entity-name.png)
- **Web API'sini kullanma**: Aşağıdaki isteği kullanın:

    **İstek**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Yanıt**
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

- **Using the Organization service**: Use the following code sample:

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

> [!NOTE]
> The <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> property is `true` for business process flow entities. You can retrieve all the business process flow entities in your instance by running the following Web API request:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## Manage security for business process flows

The custom entity that is automatically created on activating a business process flow to store business process flow instances adheres to the standard security model as for any other custom entity in Customer Engagement. This implies that privileges granted on these entities define the runtime permissions for users for business process flows.

The custom business process flow entity has organization scope. The regular create, retrieve, update and delete privileges on this entity define the permission the user would have based on his/her assigned roles. By default, when the business process flow custom entity is created, only **System Administrator** and **System Customizer** security roles are granted access to it, and you must explicitly grant permissions to the new business process flow entity (for example, **My Custom BPF**) for other security roles as required.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## Create, retrieve, update, and delete business process flow entity records (process instances)  
 The custom entity that is automatically created on activating a business process flow definition stores all the process instances for the business process flow definition. The custom entity supports the standard programmatic creation and management of records (process instances) using Web API and CRM 2011 endpoint.

> [!IMPORTANT]
> Switching to another process instance for an entity record is only supported through UI (client) or programmatically using information available in this section. You can no longer use the `SetProcess` message (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> or <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) to programmatically switch processes (set another business process flow as the active process instance) for the target entity record. 

 Lets consider the following example where we have a cross-entity business process flow, "My Custom BPF," with 3 stages: S1:Account, S2:Account, and S3:Contact. 

 ![](media/sample-bpf.png)
 
### Retrieve all the records (instances) for a business process flow entity
 If the name of your business process flow entity is "new_mycustombpf", use the following query to retrieve all the records (process instances) for your business process flow entity:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

Bu noktada, hiç örnek olmadığından yanıtınızda hiç örnek almayabilirsiniz. Bu isteği, bu konunun ilerleyen bölümlerinde iş süreci akışı tanımınızın bir örneğini oluşturduktan sonra çalıştırın.

> [!NOTE]
> İş süreci akışı varlığınızın adını nasıl alacağınızı öğrenmek için, daha önceki [İş süreci akışı varlığı](#business-process-flow-entity) bölümüne bakın.
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>İş süreci akışı kaydı (süreç örneği) oluşturma 

Kullanıcı arabirimini kullanmadan bir varlık kaydı için başka bir iş süreci akışına geçmek istiyorsanız, program aracılığıyla bir iş süreci akışı varlık kaydı (süreç örneği) oluşturun. 

İş süreci akışı varlık kaydını oluşturmak için, aşağıdaki değerleri belirtmelisiniz: 
- `@odata.bind` ek açıklamasını kullanıp tek değerli gezinti özelliğini ayarlayarak, iş süreci akışı varlık kaydını birincil varlık kaydıyla ilişkilendirin. İş süreci akışı tanımınızın birincil varlık kaydına işaret eden gezinti özelliğinin adını bulmak için [CSDL $metadata belgesini](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document) kullanın. 
- `@odata.bind` ek açıklamasını kullanıp tek değerli gezinti özelliğini ayarlayarak, iş süreci akışı varlık kaydını iş süreci akışı tanımında belirtilen geçerli bir aşamayla ilişkilendirin. İş süreci akışı tanımınızın aşama kaydına işaret eden gezinti özelliğinin adını (normalde `activestageid`) bulmak için [CSDL $metadata belgesini](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document) kullanın.

    Ayrıca, aşağıdaki Web API'si isteğini kullanarak iş süreci akışı tanımının tüm aşamaları hakkında bilgi alabilirsiniz. Burada iş süreci akışı tanımınızın kimliğinin 2669927e-8ad6-4f95-8a9a-f1008af6956f olduğu varsayılmıştır:

    **İstek**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Yanıt**

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

Ardından, bir hesap kaydı (ID=a176be9e-9a68-e711-80e7-00155d41e206) için iş süreci akışı tanımınızın örneğini oluşturmak üzere aşağıdaki isteği kullanın. Burada etkin aşama olarak süreç örneğinin ilk aşaması olan S1 (ID=9a9185f5-b75b-4bbb-9c2b-a6626683b99b) ayarlanmıştır:

**İstek**

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

**Yanıt**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

İş süreci akışı tanımınızın örneğini oluştururken etkin aşama olarak ilk aşama ***dışında*** bir aşama ayarlanmasını istiyorsanız, isteğinizde `traversedpath` değerini de sağlamalısınız. Geçilen yol (traversed path) virgülle ayrılmış süreç aşaması kimlikleri dizesidir ve iş süreci akışı örneğinin ziyaret edilen aşamalarını temsil eder. Aşağıdaki istek, bir hesap kaydı (ID=679b2464-71b5-e711-80f5-00155d513100) için örnek oluşturur ve etkin aşama olarak ikinci aşamayı (S2) (ID=19a11fc0-3398-4214-8522-cb2a97f66e4b) ayarlar.

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

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>İş süreci akışı kaydını (süreç örneği) güncelleştirme

Bir süreç örneğini güncelleştirerek sonraki veya önceki aşamaya geçebilir, süreç örneğini bırakabilir, süreç örneğini yeniden etkinleştirebilir veya süreç örneğini bitirebilirsiniz. 

#### <a name="stage-navigation"></a>Aşama gezintisi

Farklı bir aşamaya gitmek için, süreç örneği kaydını güncelleştirerek etkin aşama kimliğini değiştirmeniz ve geçilen yolu buna uygun olarak güncelleştirmeniz gerekir. İş süreci akışı örneğini güncelleştirirken yalnızca bir sonraki veya bir önceki aşamaya geçmeniz gerektiğini unutmayın.

Aşama gezintisi yapmak için, güncelleştirmek istediğiniz iş süreci akışı örneğinin kimliğini bilmeniz gerekir. İş süreci akışınızın tüm örneklerini almak için, daha önceki [İş süreci akışı varlığının tüm kayıtlarını (örneklerini) alma](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) başlığına bakın.

Güncelleştirmek istediğiniz süreç örneği kimliğinin dc2ab599-306d-e811-80ff-00155d513100 olduğunu varsayarak, S1 olan etki aşamayı S2 olarak güncelleştirmek için aşağıdaki isteği kullanın:

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

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Süreç örneğinin durumunu değiştirme: Durdur, Yeniden Etkinleştir veya Bitir 

Süreç örneğinin durumu şunlardan biri olabilir: **Etkin**, **Bitti** veya **Durduruldu**. Durum, süreç örneği kaydında aşağıdaki öznitelikler tarafından belirlenir:

- **statecode**: Süreç örneğinin durumunu görüntüler.

    |Değer|Etiket|
    |-----|-----|
    |0    |Etkin|
    |1    |Devre dışı|

- **statuscode**: Süreç örneğinin durumu hakkındaki bilgileri görüntüler.

    |Değer|Etiket|
    |-----|-----|
    |1    |Etkin|
    |2    |Bitti|
    |3    |Durduruldu|

Dolayısıyla, süreç örneğini **durdurmak** için, aşağıdaki örneği kullanın ve `statecode` ile `statuscode` değerlerini uygun şekilde ayarlayın:

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
> Bir süreç örneğini herhangi bir aşamada durdurabilirsiniz.

Benzer biçimde, süreç örneğini yeniden etkinleştirmek için, yukarıdaki kodda yer alan `statecode` ve `statuscode` değerlerini sırasıyla **0** ve **1** olarak değiştirin.

Son olarak, süreç örneğinin durumunu **Bitti** olarak ayarlamak için (bu yalnızca süreç örneğinin en son aşamasında mümkündür), yukarıdaki kodda yer alan `statecode` ve `statuscode` değerlerini sırasıyla **0** ve **2** olarak değiştirin.

#### <a name="cross-entity-navigation"></a>Çapraz varlık gezintisi

Bu örnekte çapraz varlık gezintisi için, süreç örneğinin etkin aşaması olarak son aşamayı (S3) (ID=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a) ayarlamalı, geçilen yolu buna göre güncelleştirmeli ve iş süreci akışı tanımına uygun olarak birincil varlık kaydı olarak bir kişi kaydı ayarlamalısınız.

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

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>İş süreci akışı kaydını (süreç örneği) silme

Aşağıdaki Web API'si isteğini kullanın:

**İstek**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Yanıt**

Kayıt varsa, silme işleminin başarılı olduğunu göstermek için 204 durum değeriyle normal bir yanıt alırsınız. Varlık bulunamazsa, 404 durum değeriyle bir yanıt alırsınız.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>RetrieveProcessInstances ve RetrieveActivePath iletilerini kullanma

Tüm iş süreci tanımları genelinde bir varlık kaydının tüm iş süreci akışı örneklerini almak için `RetrieveProcessInstances` iletisini (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> veya <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) kullanın. Bir varlık için döndürülen iş süreci akışı örnekleri, örneğin `modifiedon` özniteliği temel alınarak sıralanır. Örneğin en son değiştirilen iş süreci akışı örneği, döndürülen koleksiyonun *ilk* kaydı olacaktır. En son değiştirilen iş süreci akışı örneği, varlık kaydı için kullanıcı arabiriminde etkin olan örnektir.  
  
`RetrieveProcessInstances` iletisinin kullanılması sonucunda varlık kaydı için döndürülen her iş süreci akışı örnek kaydı, `processstageid` özniteliğinde etkin aşamanın kimliğini depolar. Bu kimlik, etkin aşamayı bulmak ve ardından önceki veya sonraki aşamaya geçmek için kullanılabilir. Bunu yapmak için, önce `RetrieveActivePath` iletisini (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> veya <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>) kullanarak iş süreci akışı örneğinin ve süreç akışı örneğinde var olan aşamaların etkin yolunu bulmanız gerekir.   
  
 İş süreci akışı örneğinin etkin aşama ve etkin yol bilgilerine sahip olduktan sonra, bu bilgileri kullanarak etkin yolda önceki veya sonraki aşamaya geçebilirsiniz. Aşamalarda ileriye gitme işlemi sırayla yapılmalıdır; başka bir deyişle, etkin yolda yalnızca bir sonraki aşamaya ilerlemelisiniz.   
  
 Bu iki yöntemin kullanımını ve [Kuruluş hizmeti](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)'ni kullanarak aşama gezintisini gösteren eksiksiz bir örnek kod için bkz. [Örnek: İş süreci akışlarıyla çalışma](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Varlık kaydını oluştururken iş süreci akışı uygulama

Bu bölümde Müşteri Etkileşimi'nde oluşturulan yeni varlık kayıtlarına iş süreci akışlarını otomatik olarak uygulamaya yönelik varsayılan davranış hakkında bilgi sağlanır ve yeni varlık kayıtlarına seçtiğiniz iş süreci akışını uygulamak için bu davranışı nasıl geçersiz kılabileceğiniz açıklanır.

Varsayılan olarak, kendisine birden çok iş süreci akışı tanımlanmış olan bir varlık için, sistem yeni varlık kaydına iş süreci akışını uygularken aşağıdaki çok adımlı mantığı izler:
1. İş süreci akışı tanım kayıtlarının **Workflow.PrimaryEntity** özniteliği temelinde, yeni varlık kaydına uygulanabilecek tüm iş süreci akışlarını belirleyin.
2. Geçerli kullanıcının erişebildiği iş süreci akışı tanımlarını belirleyin. İş süreci akışına erişimi saptama ve yönetme hakkında bilgi için, bu konu başlığının önceki kısımlarında [İş süreci akışları için güvenliği yönetme](#BPFSecurity) bölümüne bakın.<br/>  
3. Sistemdeki tüm iş süreci akışı tanımları varlık başına genel düzene tabidir. İş süreci akışının düzeni **Workflow.ProcessOrder** özniteliğinde depolanır. Varlığın iş süreci akışı tanımları bu düzene göre sıralanır ve sıralama değeri en düşük olan tanım seçilir.
4. Son olarak, varlık kaydı bir iş uygulamasından (uygulama modülü) oluşturulduysa, yeni varlık kaydına otomatik olarak uygulanacak iş süreci akışını seçmek için bir filtreleme düzeyi daha uygulanır. Kullanıcılar bir uygulamada çalışırken, iş uygulamasına atanmış olan güvenlik rollerinden dolayı yalnızca erişimleri olan ilgili varlıklara, iş süreci akışlarına, görünümlere ve formlara erişebilir. 
    - İş uygulamasının hiç iş süreci akışı yoksa, iş süreci akışı 3. adımda açıklandığı gibi uygulanır.
    - İş uygulamasının bir veya birden çok iş süreci akışı varsa, yalnızca uygulamada var olan iş süreci akışları uygulanabilir. Bu durumda, kullanıcı bir iş uygulaması bağlamında çalışırken, 3. adımdaki iş süreci akışlarının listesi yine filtrelenerek uygulama modülünün içindeki iş uygulamasının parçası olan iş süreci akışları bırakılır ve bunlar süreç düzeni temelinde sıralanır. 
    - İş uygulamasında varlık için iş süreci akışı yoksa veya kullanıcının erişebildiği bir iş süreci akışı yoksa, yeni varlık kaydına hiçbir iş süreci akışı uygulanmaz.

Yeni varlık kayıtlarına otomatik olarak iş süreci akışlarının varsayılan mantığını uygulamayı geçersiz kılabilirsiniz. Bunu yapmak için, yeni varlık kaydı oluştururken varlığın **ProcessId** özniteliğini şu değerlerden birine ayarlayın:
- Yeni varlık kayıtlarına iş süreci akışı ayarlamayı atlamak için **Guid.Empty** olarak ayarlayın. Varlık kayıtlarını toplu olarak oluşturuyorsanız ama bunlara iş süreci akışı uygulanmasını istemiyorsanız, bunu yapmak isteyebilirsiniz.
- Belirli bir iş süreci akışı varlığı ayarlayın (varlık başvurusu olarak). Bu durumda, sistem varsayılan mantık yerine belirtilen iş süreci akışını uygular.

Yeni varlık kaydını oluştururken **ProcessId** özniteliği için değer ayarlamazsanız, sistem daha önce açıklandığı gibi varsayılan mantığı uygular.

> [!NOTE]
> Yeni varlık kayıtlarına otomatik olarak iş süreci akışlarının varsayılan mantığını uygulamanın geçersiz kılınması, yalnızca program aracılığıyla desteklenir. Kullanıcı arabirimini kullanarak bunu yapamazsınız.

## <a name="legacy-process-related-attributes-in-entities"></a>Varlıklardaki eski süreçle ilgili öznitelikler

Varlıklarda iş süreci akışları için etkinleştirilmiş eski süreçle ilgili öznitelikler (**ProcessId**, **StageId** ve **TraversedPath** gibi) zaten kullanım dışı bırakılmıştır. Hedef varlık kayıtları için bu eski süreçle ilgili özniteliklerin işlenmesi iş süreci akışı durumunun tutarlılığını garanti etmez ve desteklenen bir senaryo ***değildir***. İş süreci akışı varlığının özniteliklerinin, daha önce [İş süreci akışı varlık kayıtlarını oluşturma, alma, güncelleştirme ve silme (süreç örnekleri)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances) bölümünde açıklandığı gibi kullanılması önerilir.

Bunun tek istisnası, yeni kayda iş süreci akışının varsayılan olarak uygulanmasını geçersiz kılmak için varlık kaydını oluştururken program aracılığıyla **ProcessId** özniteliğini değiştirmektir. Bu, önceki bölümde ([Varlık kaydını oluştururken iş süreci akışını uygulama](#ApplyBPF)) açıklanmıştır.

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>İş süreci akışları için istemci tarafı programlama desteği  
 Form betiklerinizde iş süreci akışlarıyla etkileşimli çalışmak için kullanabileceğiniz bir istemci tarafı nesnesi vardır. İş süreci akışları, kayda bir süreç uygulandığında, aşama değiştirildiğinde ya da durumu `Active`, `Finished` veya `Aborted` olarak değiştirildiğinde istemci tarafı olaylarını tetikler. Daha fazla bilgi: [formContext.data.process (İstemci API başvurusu)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Süreç, aşama ve adım sayısı üst sınırı  
 Varlığa göre, etkinleştirilmiş iş süreci akışları sayısı üst sınırı için varsayılan değer 10'dur. `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity` özniteliğini kullanarak farklı bir değer belirtebilirsiniz. Öte yandan değer 10'dan büyük olursa, süreçlerde geçiş yaptığınızda veya atanmış bir iş süreci akışı olan bir kaydı açtığınızda sisteminizin performansında düşüş yaşanabilir. Süreçler birden çok varlığa yayıldığında bu durum özellikle fark edilir olabilir.  
  
 Aşağıdaki ayarlar özelleştirilebilir değildir:  
  
-   Süreçteki varlık başına aşama sayısı üst sınırı 30'dur.  
  
-   Her aşamadaki adım sayısı üst sınırı 30'dur.  
  
-   Süreç akışına katılabilen varlık sayısı üst sınırı da 5'tir.  

