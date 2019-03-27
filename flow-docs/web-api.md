---
title: Akışlar artık Common Data Service’te depolanır ve zengin Web API’sini kullanır
description: Akışlar artık Common Data Service’te depolanır ve zengin Web API’sini kullanır.
author: stepsic-microsoft-com
ms.reviewer: deonhe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: business-applications
ms.technology: ''
ms.author: stepsic
audience: Power user
ms.openlocfilehash: ede20606d1d5ba2a97217dfbcfb3c9fffec2c017
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58353068"
---
# <a name="microsoft-flow-web-api"></a>Microsoft Flow Web API’si

Bundan sonra tüm akışlar Common Data Service'te depolanacak ve [zengin Web API'sinden](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/perform-operations-web-api) yararlanacak.

Bu içerik, Microsoft Flow'un **Çözümler** sekmesinde yer alan akışların yönetimini kapsar. **Akışlarım** bölümünde yer alan akışlar şu anda bu API'ler tarafından desteklenmemektedir.

## <a name="compose-http-requests"></a>HTTP istekleri oluşturma

İstekleri oluşturmaya başlamak için önce URL'yi oluşturmanız gerekir. Microsoft Flow Web API'si temel URL'sinin biçimi şöyledir: `https://{Organization ID}.{Regional Subdomain}.dynamics.com/api/data/v9.1/`. İki parametre:

- **Organization ID**, akışlarınızın depolandığı ortamın benzersiz adıdır. Organization ID değerini Microsoft Flow'un sağ üst kısmındaki ortam değiştiricide görebilirsiniz. **Organization ID** değerinin **Ortam Kimliği**'nden (akışın URL'sinde gösterilen GUID değeri) farklı olduğuna dikkat edin.

     ![Ortam değiştirici](media/web-api/get-organization-id.png "Ortam değiştirici")

- **Bölgesel Alt Etki Alanı**, ortamınızın konumuna bağlıdır. Microsoft Flow'da oturum açtığınızda, web sayfasının URL'sinde ortamınızın bölgesini görebilirsiniz. Bu bölge adını kullanarak aşağıdaki tabloda buna karşılık gelen alt etki alanını bulun:

     ![Akış URL'si](media/web-api/get-region-name.png "Akış URL'si")

     | Bölge         | Alt etki alanı   |
     | -------------- | ----------- |
     | Amerika Birleşik Devletleri  | crm         |
     | Güney Amerika  | crm2        |
     | Kanada         | crm3        |
     | Avrupa         | crm4        |
     | Asya Pasifik   | crm5        |
     | Avustralya      | crm6        |
     | Japonya          | crm7        |
     | Hindistan          | crm8        |
     | ABD Kamu  | crm9        |
     | Birleşik Krallık | crm11       |

Ayrıca, Çevrimiçi Yönetim API'sinde [Örnekleri Al](https://docs.microsoft.com/rest/api/admin.services.crm.dynamics.com/instances/getinstances) yöntemini kullanarak size sağlanan örnek listesini program aracılığıyla da alabilirsiniz.

Web API'sine yönelik her istekte `Accept` ve `Content-type` üst bilgileri `application/json` olarak ayarlanmış olmalıdır.

Son olarak, `Authorization` üst bilgisini bir Azure AD Taşıyıcı belirteciyle doldurun. Common Data Service'e Azure AD Taşıyıcı belirteci almayı [öğrenebilirsiniz](https://docs.microsoft.com/powerapps/developer/common-data-service/authenticate-oauth). Örneğin, bu istek:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
```

Yanıt söz konusu ortamın içindeki akışların listesini içerir:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#workflows",
    "value": [{
        "@odata.etag": "W/\"12116760\"",
        "category": 5,
        "statecode": 0,
        "workflowidunique": "00000000-0000-0000-0000-000000000001",
        "workflowid" : "00000000-0000-0000-0000-000000000002",
        "createdon": "2018-11-15T19:45:51Z",
        "_ownerid_value": "00000000-0000-0000-0000-000000000003",
        "modifiedon": "2018-11-15T19:45:51Z",
        "ismanaged": false,
        "name": "Sample flow",
        "_modifiedby_value": "00000000-0000-0000-0000-000000000003",
        "_createdby_value": "00000000-0000-0000-0000-000000000003",
        "type": 1,
        "description": "This flow updates some data in Common Data Service.",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"source\":\"NotSpecified\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\",\"tier\":\"NotSpecified\"}},\"definition\":{...}},\"schemaVersion\":\"1.0.0.0\"}"
    }]
}
```

## <a name="list-flows"></a>Akışları listeleme

Yukarıda gösterildiği gibi, `workflows` üzerinde `GET` çağrısı yaparak iş akışlarının listesini alabilirsiniz. Her iş akışının çok sayıda özelliği vardır ama en ilgili olanları şunlardır:

| Özellik adı     | Açıklama                                              |
| ----------------- | -------------------------------------------------------- |
| category          | Akışın kategorisi. Farklı türleri: 0 - klasik Common Data Service iş akışları, 1 - klasik Common Data Service iletişim kutuları, 2 - iş kuralları, 3 - klasik Common Data Service eylemleri, 4- iş süreci akışları ve 5 - otomatik, anlık veya zamanlanmış akışlar. |
| statecode         | Akışın durumu. Durum **0** - kapalı veya **1** - açık olabilir.|
| workflowuniqueid  | Akışın bu yüklemesine ilişkin benzersiz tanımlayıcı. |
| workflowid        | Tüm içeri aktarmalar genelinde akışa ilişkin benzersiz tanımlayıcı. |
| createdon         | Akışın oluşturulduğu tarih. |
| _ownerid_value    | Akışın sahibi olan kullanıcının veya takımın benzersiz tanımlayıcısı. Bu, Common Data Service'deki systemusers varlığından gelen bir tanımlayıcıdır. |
| modifiedon        | Akışın son güncelleştirildiği zaman. |
| ismanaged         | Akışın bir yönetilen çözüm yoluyla yüklendiğini belirtir. |
| name              | Akışa sizin verdiğiniz görünen ad. |
| _modifiedby_value | Akışı son güncelleştiren kullanıcı. Bu, Common Data Service'deki systemusers varlığından gelen bir tanımlayıcıdır. |
| _createdby_value  | Akışı oluşturan kullanıcı. Bu, Common Data Service'deki systemusers varlığından gelen bir tanımlayıcıdır. |
| type              | Akışın çalışan bir akış mı yoksa ek akışlar oluştururken kullanılacak bir şablon mu olduğunu belirtir. 1 - akış, 2 - etkinleştirme veya 3 - şablon. |
| açıklama       | Akışın kullanıcı tarafından sağlanan açıklaması. |
| clientdata        | Akışın connectionReferences bilgilerini ve tanımını içeren nesnenin dize olarak kodlanmış JSON öğesi. |

Ayrıca, [Common Data Service API'si verileri sorgulama belgelerinde](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/query-data-web-api) açıklandığı gibi belirli özellikleri isteyebilir, akış listesini filtreleyebilir ve daha birçok işlem yapabilirsiniz. Örneğin, bu sorgu yalnızca şu anda açık olan otomatik, anlık veya zamanlanmış akışları döndürür:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows?$filter=category eq 5 and statecode eq 1
Accept: application/json
Authorization: Bearer ey...
```

## <a name="create-a-flow"></a>Akış oluşturma

Akış oluşturmak için `workflows` koleksiyonunda `POST` çağrısı yapın. Otomatik, anlık ve zamanlanmış akışlar için gerekli özellikler şunlardır: category, name, type, primaryentity ve clientdata. Bu tür akışlarda primaryentity özelliği için `none` değerini kullanın.

Bir açıklama ve durum kodu da sağlayabilirsiniz.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
        "category": 5,
        "statecode": 0,
        "name": "Sample flow name",
        "type": 1,
        "description": "This flow reads some data from Common Data Service.",
        "primaryentity":"none",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"connectionName\":\"shared-commondataser-00000000-0000-0000-0000-000000000004\",\"source\":\"Invoker\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\"}},\"definition\":{\"$schema\": \"https:\/\/schema.management.azure.com\/providers\/Microsoft.Logic\/schemas\/2016-06-01\/workflowdefinition.json#\",\"contentVersion\": \"1.0.0.0\",\"parameters\": {\"$connections\": {\"defaultValue\": {},\"type\": \"Object\"},\"$authentication\": {\"defaultValue\": {},\"type\": \"SecureObject\"}},\"triggers\": {\"Recurrence\": {\"recurrence\": {\"frequency\": \"Minute\",\"interval\": 1},\"type\": \"Recurrence\"}},\"actions\": {\"List_records\": {\"runAfter\": {},\"metadata\": {\"flowSystemMetadata\": {\"swaggerOperationId\": \"GetItems_V2\"}},\"type\": \"ApiConnection\",\"inputs\": {\"host\": {\"api\": {\"runtimeUrl\": \"https:\/\/firstrelease-001.azure-apim.net\/apim\/commondataservice\"},\"connection\": {\"name\": \"@parameters('$connections')['shared_commondataservice']['connectionId']\"}},\"method\": \"get\",\"path\": \"\/v2\/datasets\/@{encodeURIComponent(encodeURIComponent('default.cds'))}\/tables\/@{encodeURIComponent(encodeURIComponent('accounts'))}\/items\",\"queries\": {\"$top\": 1},\"authentication\": \"@parameters('$authentication')\"}}},\"outputs\": {}}},\"schemaVersion\":\"1.0.0.0\"}"
}
```

En önemli bölüm, akışın kullandığı connectionReferences bilgilerini ve akışın [tanımını](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language) içeren `clientdata` bölümüdür. connectionReferences, akışın kullandığı her bağlantının eşlemeleridir.

Üç özellik vardır:

| Özellik adı  | Açıklama                                                 |
| -------------- | ----------------------------------------------------------- |
| connectionName | Bağlantıyı tanımlar. connectionName değerini, **Bağlantılar** sayfasına gidip bağlantının URL'sinden kopyalayarak görebilirsiniz. |
| source         | `Embedded` veya `Invoker`. `Invoker` yalnızca anlık akışlarda (kullanıcının bir düğme seçerek çalıştırdığı akışlar) geçerlidir ve bağlantıyı son kullanıcının sağlayacağını belirtir. Bu durumda connectionName yalnızca tasarım zamanında kullanılır. Bağlantının `Embedded` olması, belirttiğiniz connectionName değerinin her zaman kullanılacağı anlamına gelir. |
| id             | Bağlayıcının tanımlayıcısı. Bu id özelliği her zaman `/providers/Microsoft.PowerApps/apis/` ile başlar ve ardından bağlayıcı adı gelir. Bağlayıcı adını bağlantının URL'sinden veya **Bağlayıcılar** sayfasında bağlayıcıyı seçerek kopyalayabilirsiniz. |

`POST` isteğini yürüttükten sonra, yeni akışınızın `workflowid` değerini içeren `OData-EntityId` üst bilgisini alırsınız.

## <a name="update-a-flow"></a>Akışı güncelleştirme

İş akışında `PATCH` çağrısı yaparak akışı güncelleştirebilir, açabilir veya kapatabilirsiniz. Bu çağrıları yapmak için `workflowid` özelliğini kullanın. Örneğin, aşağıdaki çağrıyla akışın açıklamasını ve sahibini güncelleştirebilirsiniz:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "description" : "This flow will ensure consistency across systems.",
    "ownerid@odata.bind": "systemusers(00000000-0000-0000-0000-000000000005)",
}
```

> [!NOTE]
> Sahibi değiştirme söz diziminde `odata.bind` biçimi kullanılır. Başka bir deyişle, \_ownerid_value alanını doğrudan eklemek yerine özellik adının sonuna `@odata.bind` ekler ve ardından ID değerini `systemusers()` içine yerleştirirsiniz.

Başka bir örnekte, şu çağrıyla akışı açabilirsiniz:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "statecode" : 1
}
```

### <a name="delete-a-flow"></a>Akışı silme

Basit bir `DELETE` çağrısıyla akışı silebilirsiniz:

```http
DELETE https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
```

> [!NOTE]
> Açılmış olan akışları silemezsiniz. Önce akışı kapatmanız gerekir (yukarıdaki **Akışı güncelleştirme** bölümüne bakın). Yoksa şu hatayı görürsünüz: `Cannot delete an active workflow definition.`

## <a name="get-all-users-with-whom-a-flow-is-shared"></a>Akışın paylaşıldığı tüm kullanıcıları alma

Erişimi olan kullanıcıları listelemek için Common Data Service'de bir *işlev* kullanılır. Bu işler yalnızca `Target` parametresini alır:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/RetrieveSharedPrincipalsAndAccess(Target=@tid)?@tid={'@odata.id':'workflows(00000000-0000-0000-0000-000000000002)'}
Accept: application/json
Authorization: Bearer ey...
```

`Target` parametresi, `@odata.id` adlı tek özelliği olan JSON benzeri bir dizedir. Yukarıdaki örneğin iş akışı kimliğini değiştirin. Şunu döndürür:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.RetrieveSharedPrincipalsAndAccessResponse",
    "PrincipalAccesses": [
        {
            "AccessMask": "ReadAccess",
            "Principal": {
                "@odata.type": "#Microsoft.Dynamics.CRM.systemuser",
                "ownerid": "00000000-0000-0000-0000-000000000005"
            }
        }
    ]
}
```

## <a name="share-or-unshare-a-flow"></a>Akışı paylaşma veya paylaşımını kaldırma

`GrantAccess` eylemini kullanarak akışı paylaşabilirsiniz.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/GrantAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "PrincipalAccess": {
        "Principal": {
            "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
            "ownerid" : "00000000-0000-0000-0000-000000000005"
        },
        "AccessMask": "ReadAccess"
    }
}
```

`AccessMask` parametresi, farklı izin düzeyleri için aşağıdaki değerleri içeren bir alandır:

| Ad         | Açıklama                                          |
| ------------ | ---------------------------------------------------- |
| None         | Erişim yok.                                           |
| ReadAccess   | Akışı okuma hakkı.                          |
| WriteAccess  | Akışı güncelleştirme hakkı.                        |
| DeleteAccess | Akışı silme hakkı.                        |
| ShareAccess  | Akışı paylaşma hakkı.                         |
| AssignAccess | Akışın sahibini değiştirme hakkı.           |

İzinleri virgülle birleştirebilirsiniz; örneğin, `ReadAccess,WriteAccess` değerini geçirerek akışı hem okuma hem de güncelleştirme izni sağlayabilirsiniz.

`RevokeAccess` eylemiyle akışın *paylaşımını kaldırabilirsiniz*. İşte bir örnek:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/RevokeAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "Revokee": {
        "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
        "ownerid" : "00000000-0000-0000-0000-000000000005"
    }
}
```

`RevokeAccess`, `AccessMask` içinde verilen tüm izinleri kaldırır.

## <a name="export-flows"></a>Akışları dışarı aktarma

Akışları bir .zip dosyasına aktarmak için `ExportSolution` eylemini kullanın. Önce, istediğiniz akışları bir [çözüme](https://flow.microsoft.com/blog/solutions-in-microsoft-flow/) ekleyin.

Akışınız çözüm içinde olduğunda, aşağıdaki eylemi çağırın:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ExportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "SolutionName" : "Awesome solution 1",
    "Managed": false
}
```

`ExportSolution`, `ExportSoutionFile` özelliğinde base 64 kodlamalı bir dize döndürür.

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.ExportSolutionResponse",
    "ExportSolutionFile": "UEsDBBQAAgAI..."
}
```

Ardından bu dosyayı kaynak denetimine kaydedebilir ve/veya istediğiniz sürüm yönetimi veya dağıtım sisteminde kullanabilirsiniz.

## <a name="import-flows"></a>Akışları içeri aktarma

Çözümü içeri aktarmak için `ImportSolution` çağrısı yapın.

| Özellik adı                    | Açıklama                               |
| -------------------------------- | ----------------------------------------- |
| OverwriteUnmanagedCustomizations | Common Data Service'de bu akışların örnekleri varsa, bunları içeri aktarmak için bu bayrağın `true` olarak ayarlanması gerekir. Aksi takdirde bunlar üzerine yazılmaz. |
| PublishWorkflows                 | Klasik Common Data Service iş akışlarının içeri aktarıldığında etkinleştirileceğini belirtir. Bu ayar, diğer iş akışı türlerinde geçerli değildir. |
| ImportJobId                      | İçeri aktarma işini izlemek için yeni, benzersiz bir GUID sağlar. |
| CustomizationFile                | Çözümü içeren base 64 kodlamalı bir zip dosyası. |

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ImportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "OverwriteUnmanagedCustomizations": false,
    "PublishWorkflows" : true,
    "ImportJobId" : "00000000-0000-0000-0000-000000000006",
    "CustomizationFile" : "UEsDBBQAAgAI..."
}
```

İçeri aktarma uzun süre çalışan bir işlem olduğundan, ImportSolution eyleminin yanıtı `204 No content` olacaktır. İlerleme durumunu izlemek için, `importjobs` nesnesinde `GET` çağrısı yapın ve özgün `ImportSolution` eylemine eklemiş olduğunuz `ImportJobId` değerini sağlayın.

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/importjobs(00000000-0000-0000-0000-000000000006)
Accept: application/json
Authorization: Bearer ey...
```

Bu çağrı, `progress` (tamamlanma yüzdesi), `startedon` ve `completedon` (içeri aktarma bittiyse) bilgileriyle içeri aktarma işleminin durumunu döndürür.

İçeri aktarma işlemi başarıyla tamamlandıktan sonra, hedef ortamda `connectionNames` büyük olasılıkla farklı olacağından (bağlantıların var olduğunu varsayarsak) akış için bağlantıları yeniden ayarlamanız gerekir. Hedef ortamda yeni bağlantılar ayarlıyorsanız, akışların sahibi bunları Microsoft Flow tasarımcısında oluşturmalıdır. Yeni ortamda bağlantılar zaten ayarlanmışsa, bağlantıların adlarını akışın `clientData` değerine `PATCH` ile ekleyebilirsiniz.
