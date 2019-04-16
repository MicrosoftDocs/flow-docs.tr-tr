---
title: Microsoft Flow’u web siteleri ve uygulamalarla tümleştirme | Microsoft Docs
description: Microsoft Flow deneyimlerini web sitenize veya uygulamanıza ekleyin.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: barathb
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 47d44b2c97275add492153d85138b7d11b554530
ms.sourcegitcommit: 3c7822c7207cfa51d0274e9647ef02e5ea1d999f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58321422"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Microsoft Flow’u web siteleri ve uygulamalarla tümleştirme

Kullanıcılarınıza, kişisel veya profesyonel görevlerini otomatik hale getirmeleri için kolay bir yol sunmak üzere, *akış pencere öğelerini* kullanarak Microsoft Flow'u uygulamanıza veya web sitenize ekleyin.

Akış pencere öğeleri konak belgesinde yer alan iframe'lerdir. Bu belgede Microsoft Flow tasarımcısındaki bir sayfaya işaret edilir. Bu pencere öğeleri belirli Microsoft Flow işlevlerini üçüncü taraf uygulamayla tümleştirir.

Pencere öğeleri basit olabilir. Örneğin, konakla iframe arasında hiçbir iletişim olmadan şablon listesini işleyen pencere öğesi basit bir pencere öğesidir. Pencere öğeleri karmaşık da olabilir. Örneğin, bir şablondan akış sağlayan ve ardından konakla pencere öğesi arasında iki yönlü iletişim üzerinden akışı tetikleyen pencere öğesi karmaşıktır.

## <a name="prerequisites"></a>Önkoşullar

- **Microsoft Hesabı** ya da
- İş veya okul hesabı

## <a name="use-the-unauthenticated-widget"></a>Kimliği doğrulanmamış pencere öğesi kullanma
Kimliği doğrulanmış bir şablon kullanmak için, bunu iframe'de doğrudan konak uygulamaya ekleyin. JS SDK'sı veya erişim belirtecine ihtiyacınız yoktur. 

### <a name="show-templates-for-your-scenarios"></a>Senaryolarınıza ilişkin şablonları gösterme
Başlangıç olarak, Microsoft Flow şablonlarını web sitenizde göstermek için şu kodu ekleyin:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

| Parametre | Açıklama |
| --- | --- |
| yerel ayar |Şablon görünümü için dört harfli dil ve bölge kodu. Örneğin, `en-us` Amerikan İngilizcesi'ni ve `de-de`, Almanca'yı temsil eder. |
| arama terimi |Görünümde göstermek istediğiniz şablonlara ilişkin arama terimi. Örneğin, Wunderlist şablonlarını göstermek için `wunderlist` öğesini arayın. |
| şablon sayısı |Görünümde göstermek istediğiniz şablon sayısı. |
| hedef |Kullanıcılar şablonu seçtiğinde açılan sayfa. Şablonla ilgili ayrıntıları göstermek için `details` girin veya Microsoft Flow tasarımcısını açmak için `new` girin. |
| parameters.{name} |Akışa geçirmek için ek bağlam. |
| templateCategory | Belirtilen şablon kategorisini filtreler                     | 

Hedef parametre `new` olursa, kullanıcı bir şablon seçtiğinde Microsoft Flow tasarımcısı açılır. Ardından kullanıcılar tasarımcıda akış oluşturabilir. Pencere öğesiyle ilgili eksiksiz bir deneyim elde etmek istiyorsanız bir sonraki bölüme bakın.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Akış şablonuna ek parametreleri geçirme

Kullanıcı, web sitenizde veya uygulamanızda belirli bir bağlamda ise bu bağlamı akışa geçirmek isteyebilirsiniz. Örneğin, bir kullanıcı Wunderlist'te belirli bir listeye bakarken *Notify me when an item is added to a list* (Listeye bir öğe eklendiğinde bana bildir) için bir şablon açabilir. Liste kimliğini akışa bir *parametre* olarak geçirmek için bu adımları izleyin:

1. Yayımlamadan önce, akış şablonunda parametreyi tanımlayın. Parametre şöyle görünür: `@{parameters('parameter_name')}`.
1. Parametreyi iframe src içine alın. Örneğin, **listName** adlı bir parametreniz varsa `&parameters.listName={the name of the list}` öğesini ekleyin.

### <a name="full-sample"></a>Tam örnek

İlk dört Almanca Wunderlist şablonunu görüntülemek ve kullanıcıyı **myCoolList** ile başlatmak için bu kodu kullanın:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Kimliği doğrulanmış akış pencere öğelerini kullanma

Aşağıdaki tabloda kullanıcı kimlik doğrulaması erişim belirteci kullanılarak pencere öğesinin içinde tam deneyimi destekleyen Microsoft Flow pencere öğelerinin listesi gösterilir. Pencere öğelerini eklemek ve gerekli kullanıcı erişim belirtecini sağlamak için Microsoft Flow'un Javascript Yazılım Geliştirme Seti'ni (JS SDK) kullanmanız gerekir.

| Pencere öğesi türü    | Desteklenen özellik                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Akışlar          | Kişisel ve paylaşılan akışlar için bir sekmede akış listesini gösterir. Mevcut şablonu düzenleyin ya da şablondan veya sıfırdan yeni akış oluşturun. | 
| FlowCreation   | Konak uygulamanın sağladığı şablon kimliğinden bir akış oluşturur.                                                                | 
| Runtime        | Konak uygulamanın sağladığı el ile veya karma tetikleyiciyi tetikler.                                                        | 
| ApprovalCenter | Onay istekleri ekler ve onayları gönderir.                                                                                        | 
| Şablonlar      | Şablon listesi gösterir. Kullanıcı yeni akış oluşturmak için bir şablon seçer.                                                                         | 

Kullanıcıların, (Microsoft Flow'a gitmek yerine) doğrudan web sitenizden veya uygulamanızdan akış oluşturmasını ve yönetmesini sağlamak için, kimliği doğrulanmış Flow SDK'sını kullanın. Kimliği doğrulanmış SDK'yı kullanmak için Microsoft Hesabı'nda veya Azure Active Directory'de kullanıcının oturumunu açmanız gerekir.

> [!NOTE]
> Pencere öğelerini kullanırken Microsoft Flow markasını gizlemenin hiçbir yolu yoktur.

## <a name="widget-architecture"></a>Pencere öğesi mimarisi

Microsoft Flow pencere öğeleri, Microsoft Flow'a başvuran bir iframe'i konak uygulamaya ekleme yoluyla çalışır. Konak, Microsoft Flow pencere öğesine gereken erişim belirtecini sağlar. Microsoft Flow'un JS SDK'sı konak uygulamanın pencere öğesi yaşam döngüsünü başlatmasına ve yönetmesine olanak tanır.

![pencere öğesi mimarisi](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>JS SDK ayrıntıları

Microsoft Flow takımı JS SDK'yı, Flow pencere öğelerini üçüncü taraf uygulamalara tümleştirmeyi kolaylaştırmak için sağlar. Flow hizmetinde genel bağlantı olarak sağlanan Flow JS SDK'sı, konak uygulamanın pencere öğesinden olayları işlemesine ve pencere öğesine eylemler göndererek Flow uygulamasıyla etkileşim kurmasına olanak tanır. Pencere öğesi olayları ve eylemleri pencere öğesinin türüne özgüdür.

### <a name="widget-initialization"></a>Pencere öğesi başlatma

Pencere öğesini başlatmadan önce konak uygulamaya Flow JS SDK'sı başvurusu eklenmelidir.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

JSON nesnesinde isteğe bağlı hostName ve locale değerlerini geçirerek bir JS SDK örneği oluşturun.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US',
}); 
```

| Ad     | Gerekli/İsteğe Bağlı | Açıklama                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | İsteğe bağlı          | Microsoft Flow konak adı, örneğin https://flow.microsoft.com        | 
| `locale`   | İsteğe bağlı          | Pencere öğesi için istemcinin yerel ayarı (geçirilmezse varsayılan olarak `en-Us` kullanılır) | 


JS SDK örneği oluşturulduktan sonra konak uygulamadaki bir üst öğede Microsoft Flow pencere öğesini başlatabilir ve ekleyebilirsiniz. Bunu yapmak için HTML div'i ekleyin:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Ardından Microsoft Flow pencere öğesini JS SDK renderWidget() yöntemiyle başlatın. Pencere öğesi türünü ve buna karşılık gelen ayarları sağlamayı unutmayın.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flow-div',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {},
});
```

Burada konak uygulamanın boyutlarıyla eşleşecek şekilde değiştirebileceğiniz kapsayıcı için örnek stil gösterilmiştir.

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

Bunlar, `renderWidget()` yönteminin parametreleridir: 

| Parametre        | Gerekli/İsteğe Bağlı | Açıklama                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Gerekli          | Pencere öğesinin ekleneceği konak sayfasındaki DIV öğesinin kimliği                      | 
| `environmentId`    | İsteğe bağlı          | Pencere öğelerine bir ortam kimliği gerekir. Kimlik sağlamazsanız, varsayılan ortam kullanılır. | 
| `flowsSettings`    | İsteğe bağlı          | Microsoft Flow ayarları nesnesi                                                                        | 
| `templateSettings` | İsteğe bağlı          | Şablon ayarları nesnesi                                                                    | 
| `approvalSettings` | İsteğe bağlı          | Onay ayarları nesnesi                                                                    | 

### <a name="access-tokens"></a>Erişim belirteçleri

JS SDK `renderWidget()` çalıştırıldıktan sonra, JS SDK Microsoft Flow pencere öğesi URL'sine işaret eden bir iframe başlatır. Bu URL, sorgu dizesi parametrelerinde tüm ayarları içerir. Konak uygulamanın pencere öğesini başlatmadan önce kullanıcı için bir Microsoft Flow erişim belirteci (hedef kitle https://service.flow.microsoft.com) ile Azure Active Directory JWT belirteci) alması gerekir. Pencere öğesi konaktan erişim belirteci istemek için bir `GET_ACCESS_TOKEN` olayı tetikler. Konak olayı işlemeli ve belirteci pencere öğesine geçirmelidir:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

Belirtecin bakımı ve istendiğinde geçerli bir süre sonu tarihiyle pencere öğesine geçirilmesi konak uygulamanın sorumluluğundadır. Pencere öğesi daha uzun süre açık kalırsa, konak belirtecin süresinin dolup dolmadığını denetlemeli ve pencere öğesine geçirmeden önce gerekiyorsa belirteci yenilemelidir.

### <a name="detecting-if-the-widget-is-ready"></a>Pencere öğesinin hazır olup olmadığını algılama

Başarılı bir başlatma işleminden sonra, pencere öğesi hazır olduğunu bildirmek için bir olay tetikler. Konak `WIDGET_READY` olayını dinleyebilir ve ek konak kodunu yürütebilir.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Pencere öğesi ayarları

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings, Microsoft Flow pencere öğesinin işlevselliğini özelleştirmek için kullanılabilir.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Parametre | Gerekli/İsteğe Bağlı | Açıklama | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Gerekli | Kullanıcı Flow pencere öğesinde **Boş akış oluştur** düğmesini seçtiğinde şabonun GUID değerini kullanın | 
| `flowsFilter` | İsteğe bağlı | Microsoft Flow pencere öğesi akışları listelerken sağlanan filtreyi uygular. Örneğin, belirli bir SharePoint sitesine başvuran akışları gösterebilirsiniz. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | İsteğe bağlı | Microsoft Flow pencere öğesinde varsayılan olarak etkin sekmeyi gösterir. <br /> Örneğin, <br /> ```tab:'sharedFlows' ``` Takım sekmesini görüntüler<br /> ve ``` tab:'myFlows' ``` da Akışlarım sekmesini görüntüler. |   

### <a name="templatessettings"></a>TemplatesSettings 

Bu Flows, FlowCreation ve Templates pencere öğeleri gibi şablondan akış oluşturmanıza olanak tanıyan tüm pencere öğelerine uygulanır.

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| Parametre |Gerekli/İsteğe Bağlı | Açıklama                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | İsteğe bağlı          | Şablondan akış oluştururken kullanılacak tasarım zamanı parametreleri, örneğin: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | İsteğe bağlı          | Geçerli değerler 'new' veya 'details' değerleridir. Bu 'details' olarak ayarlandığında, şablondan akış oluştururken ayrıntı sayfası gösterilir.     |
| `pageSize` | İsteğe bağlı          | Görüntülenecek şablon sayısı. Varsayılan boyut = 6 | 
| `searchTerm` | İsteğe bağlı          | Sağlanan arama terimiyle eşleşen şablonları görüntüler| 
| `templateCategory` | İsteğe bağlı          | Belirli bir kategorideki şablonları görüntüler| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

ApprovalCenter pencere öğelerine uygulanır.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Parametre | Gerekli/İsteğe Bağlı | Açıklama | 
|------------|-------------------|--------------| 
| `hideLink`| İsteğe bağlı | Bu `true` olarak ayarlandığında, pencere öğesi alınan ve gönderilen onay bağlantılarını gizler | 
| `autoNavigateToDetails`| İsteğe bağlı | Bu `true` olarak ayarlandığında ve tek bir onay olduğunda, pencere öğesi onay ayrıntılarını otomatik olarak açar | 
| `approvalsFilter`| İsteğe bağlı | Onay pencere öğesi onayları listelerken belirtilen onay filtresini uygular, örneğin:    Onay pencere öğesi onayları listelerken belirtilen onay filtresini uygular, örneğin: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| İsteğe bağlı | Flow pencere öğesinde varsayılan olarak gösterilecek etkin sekme. <br/> Geçerli değerler: 'receivedApprovals', 'sentApprovals' | 
| `showSimpleEmptyPage`| İsteğe bağlı | Hiç onay olmadığında boş bir sayfa gösterir | 
| `hideInfoPaneCloseButton` | İsteğe bağlı | Bilgi bölmesi Kapat düğmesini gizler (veya konağın zaten bir Kapat düğmesi vardır) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Pencere öğesi olayları

Microsoft Flow pencere öğesi, konağın pencere öğesi yaşam döngüsü olaylarını dinlemesini sağlayan olayları destekler. Microsoft Flow pencere öğesi iki tür olayı destekler: tek yönlü bildirim olayları (örneğin, PencereÖğesi\_Hazır) ve konaktan verileri getirmek için pencere öğesinden tetiklenen olaylar (Erişim\_Belirteci\_Al). Konağın pencere öğesinden tetiklenen belirli olayları dinlemek için widget.listen() yöntemini kullanması gerekir.

### <a name="usage"></a>Kullanım

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Pencere öğesi türünün desteklediği olaylar

| Pencere öğesi olayı      | Ayrıntılar                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Pencere öğesi başarıyla yüklendi                                      | 
| `WIDGET_RENDERED`   | Pencere öğesi yüklendi ve kullanıcı arabirimi işlemesi tamamlandı                      | 
| `GET_ACCESS_TOKEN`  | Kullanıcı erişim belirtecini eklemek için pencere öğesi isteği                      | 
| `GET_STRINGS`       | Konağın pencere öğesinde gösterilen bir dizi kullanıcı arabirimi dizesini geçersiz kılmasına izin verir | 

### <a name="runtime-widget"></a>Çalışma zamanı pencere öğesi

| Pencere öğesi olayı                    | Ayrıntılar                                     | Veriler                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Tetiklendi ve akış çalıştırması başlatıldı      |           | 
| `RUN_FLOW_COMPLETED`              | Akış çalıştırması başarıyla tetiklendi             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | Akış çalıştırmasında kullanıcı Bitti düğmesini seçti       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Akış çalıştırmasında kullanıcı İptal düğmesini seçti     |           | 
| `FLOW_CREATION_SUCCEEDED`         | Akış başarıyla oluşturuldu           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Konağın pencere öğesini kapatması gerektiğinde tetiklendi |       | 

### <a name="flow-creation-widget"></a>Akış Oluşturma pencere öğesi

| Pencere öğesi olayı             | Ayrıntılar                                  | Veriler  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Akış oluşturulamadı                     |       | 
| `WIDGET_CLOSE`             | Konağın pencere öğesini kapatması gerektiğinde tetiklendi  |       | 
| `TEMPLATE_LOAD_FAILED`     | Şablon yüklenemedi              |       | 
| `FLOW_CREATION_SUCCEEDED`  | Akış başarıyla oluşturuldu        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Onay pencere öğesi

| Pencere öğesi olayı                      | Ayrıntılar                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Alınan onay durumu değiştirildi  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Gönderilen onay durumu değiştirildi      | 

**GET\_STRINGS** olayı, pencere öğesinde gösterilen kullanıcı arabirimi öğelerinden bazılarının metnini özelleştirmenize olanak tanır. Aşağıdaki dizeler özelleştirilebilir:

| Dize anahtarı                     | Pencere öğesinde kullanımı                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Hem akış oluşturma hem de çalışma zamanı pencere öğesinde, akış oluşturma düğmesinde görüntülenen metin                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | Akış oluşturma pencere öğesinde akış adı olarak kullanılacak ilk değer. Yalnızca allowCustomFlowName ayarı etkinleştirildiğinde kullanılır. | 
| `FLOW_CREATION_HEADER`           | Hem akış oluşturma hem de çalışma zamanı pencere öğesinde akış oluşturulurken kullanılacak üst bilgi                                                    | 
| `INVOKE_FLOW_HEADER`             | Çalışma zamanı pencere öğesinde akışı çağırırken kullanılacak üst bilgi                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Çalışma zamanı pencere öğesinde akışı çağırmak/çalıştırmak için kullanılan düğmede görüntülenen metin                                                       | 

### <a name="example"></a>Örnek

Varsayılan değeri geçersiz kılmak için dize anahtarı ve metninden oluşan bir anahtar-değer çiftinin bulunduğu JSON nesnesini geçirerek `widgetDoneCallback` çağrısı yapın.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Pencere öğesi eylemleri

Konak pencere öğesine belirli bir eylem veya ileti göndermek için pencere öğesi eylemlerini kullanır. Pencere öğesi JS SDK'sı pencere öğesine ileti veya JSON yükü göndermek için `notify()` yöntemini sağlar. Her pencere öğesi belirli bir yük imzasını destekler.

### <a name="usage"></a>Kullanım

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Örnek 

Çalışma zamanı pencere öğesine aşağıdaki komutu göndererek bir akış çağırın 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Çalışma zamanı pencere öğesi

| Pencere öğesi eylemi                               | Ayrıntılar                                                      | Parametre arabirimi  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Akışın çalıştırılmasını tetikler                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Şablon tarafından akışın çalıştırılmasını tetikler                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Akışın tetikleyici şemasını alır                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Bekleyen etkinlikleri iptal eder ve bir WIDGET_CLOSE olayı tetikler |                      | 

### <a name="flow-creation-widget"></a>Akış Oluşturma pencere öğesi

| Pencere öğesi eylemi                               | Ayrıntılar                                                      | Parametre arabirimi  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Seçilen şablon için bir akış oluşturur                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Seçilen şablon tanımı için bir akış oluşturur          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Bekleyen etkinlikleri iptal eder ve bir WIDGET_CLOSE olayı tetikler |                      | 

### <a name="approval-widget"></a>Onay pencere öğesi

| Pencere öğesi eylemi  | Ayrıntılar                                           | Parametre arabirimi  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Onay ayrıntılarının görüntülendiği bilgi bölmesini kapatır  | Yok                  | 

## <a name="configuring-your-client-application"></a>İstemci uygulamanızı yapılandırma

İstemci uygulamanızı Flow Hizmeti Kapsamları (Temsilci İzinleri) ile yapılandırmanız gerekir. Pencere öğesi tümleştirmesinde kullanılan Azure Active Directory (AAD) uygulaması 'code grant' yetkilendirme akışını kullanıyorsa, AAD uygulamasının Microsoft Flow tarafından desteklenen temsilci izinleriyle önceden yapılandırılması gerekir. Bu, uygulamanın şunları yapmasını sağlayan temsilci izinleri verir:

-   Onayları yönetme
-   Onayları okuma
-   Etkinlikleri okuma
-   Akışları yönetme
-   Akışları okuma

Bir veya birden çok temsilci izni seçmek için şu adımları izleyin:

1.  Git https://portal.azure.com 
2.  **Azure Active Directory**'yi seçin.
3.  **Yönet**'in altında **Uygulama kayıtları**'nı seçin.
4.  Flow hizmeti kapsamları için yapılandırılacak üçüncü taraf uygulamasını girin.
5.  **Ayarlar**'ı seçin.
      ![pencere öğesi mimarisi](../media/embed-flow-dev/AAD-App-Settings.png)
6. **API erişimi**/ alanında **Gerekli izinler**'i seçin.
7. **Ekle**'yi seçin.
8. **API seçin** öğesini seçin.
      ![pencere öğesi mimarisi](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. **Microsoft Flow hizmeti** için arama yapın ve bu hizmeti seçin. Not: Microsoft Flow hizmetini görebilmeniz için, kiracınızın en az bir AAD kullanıcısının Flow portalında (<https://flow.microsoft.com>) oturum açmış olması gerekir.
10. Uygulamanız için gerekli Flow kapsamlarını seçtikten sonra **Kaydet**'i seçin.
      ![pencere öğesi mimarisi](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Şimdi uygulamanız JWT belirtecinde \'scp' talebindeki temsilci izinlerini içeren bir Flow Hizmeti belirteci alacaktır.

## <a name="sample-application-embedding-flow-widgets"></a>Akış pencere öğelerinin eklendiği örnek uygulama 

Konak sayfasına akış pencere öğeleri eklemeyi deneyebilmeniz için, kaynaklar bölümünde örnek bir JavaScript Tek Sayfalı Uygulaması (SPA) sağlanmıştır. Örnek uygulamayı kullanmak için örtük onay akışının etkinleştirildiği bir AAD uygulamasının kaydedilmesi gerekir.

### <a name="registering-an-aad-app"></a>AAD uygulamasını kaydetme

1.  [Azure portalında](https://portal.azure.com/) oturum açın.
2.  Sol gezinti bölmesinde **Azure Active Directory**'yi seçin ve sonra da **Uygulama kayıtları** (Önizleme) \> Yeni kayıt seçeneğini belirtin.
3.  **Uygulamayı kaydet** sayfası görüntülendiğinde, uygulamanız için ad girin.
4.  **Desteklenen hesap türleri**'nin altında, herhangi bir kuruluş dizinindeki **Hesaplar**'ı seçin.
5.  **Yeniden yönlendirme URL'si** bölümünde web platformunu seçin ve değeri, web sunucunuz temelinde uygulamanın URL'sine ayarlayın.  Örnek uygulamayı çalıştırmak için bu değeri http://localhost:30662/ olarak yapılandırın.
6.  **Kaydet**'i seçin.
7.  Uygulamanın **Genel Bakış** sayfasında uygulama (istemci) kimliği değerini not alın.
8.  Örneğin etkinleştirilmesi için [örtük onay akışı](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) gerekir. Kayıtlı uygulamanın sol gezinti bölmesinde **Kimlik doğrulaması**'nı seçin.
9.  **Gelişmiş ayarlar**'daki **Örtük onay**'ın altında hem **Kimlik belirteçleri** hem de **Erişim belirteçleri** onay kutularını etkinleştirin. Bu uygulama kullanıcıların oturumunu açacağı ve Flow API'yi çağıracağı için, kimlik belirteçleri ve erişim belirteçleri gereklidir.
10. **Kaydet**’i seçin.

### <a name="running-the-sample"></a>Örneği çalıştırma
<!-- todo where should I download from? -->
<!-- todo is this a misspelling: applicaionConfig -->
1.  Örneği indirin ve bilgisayarınızdaki yerel bir klasöre kopyalayın.
2.  FlowSDKSample klasörünün altındaki index.html dosyasını açın ve `clientID` değerini daha önce kaydettiğiniz uygulama kimliğiyle güncelleştirmek için `applicaionConfig` ayarını değiştirin.
    ![pencere öğesi mimarisi](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  Örnek uygulama **Flows.Read.All** ve **Flow.Manage.All** Flow kapsamlarını kullanacak şekilde yapılandırılmıştır. **applicationConfig** nesnesinde **flowScopes** özelliğini güncelleştirerek ek kapsamlar yapılandırabilirsiniz.
4.  Bağımlılığı yüklemek ve örnek uygulamayı çalıştırmak için şu komutları çalıştırın:
    > \> npm install \> node server.js
5. Tarayıcıyı açın ve http://localhost:30662 girin.
6. AAD'de kimlik doğrulaması yapmak ve bir akış erişim belirteci almak için **Oturum aç** düğmesini seçin.
7. **Erişim Belirteci** metin kutusunda erişim belirteci vardır.
    ![pencere öğesi mimarisi](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. İlgili pencere öğelerini eklemek için **Akışları Yükle pencere öğesi**'ni veya **Şablonları Yükle pencere öğesi**'ni seçin.
    ![pencere öğesi mimarisi](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

Örnek uygulama [indirme bağlantısı](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip).

## <a name="resources"></a>Kaynaklar

### <a name="widget-test-pages"></a>Pencere öğesi test sayfaları

Pencere öğesi tümleştirmesi ve ayarları hakkında daha fazla bilgi edinin:

- Templates pencere öğesi: <[https://flow.microsoft.com/en-us/test/templateswidget/](https://flow.microsoft.com/en-us/test/templateswidget/)>
- FlowCreation pencere öğesi: <[https://flow.microsoft.com/en-us/test/flowcreationwidget/](https://flow.microsoft.com/en-us/test/flowcreationwidget/)>
- Runtime pencere öğesi: <[https://flow.microsoft.com/en-us/test/runtimewidget/](https://flow.microsoft.com/en-us/test/runtimewidget/)>
- Approvals center pencere öğesi: <[https://flow.microsoft.com/en-us/test/approvalcenterwidget/](https://flow.microsoft.com/en-us/test/approvalcenterwidget/)>
- Flows pencere öğesi: <[https://flow.microsoft.com/en-us/test/managewidget/](https://flow.microsoft.com/en-us/test/managewidget/)>

### <a name="supported-widget-locales"></a>Desteklenen pencere öğesi yerel ayarları

Başlatılan yerel ayar listelenmiyorsa, Flow varsayılan olarak desteklenen en yakın yerel ayarı kullanacaktır.

| Yerel ayar     | Dil                   | 
|------------|----------------------------| 
| bg-bg      | Bulgarca (Bulgaristan)       | 
| ca-es      | Katalanca (İspanya)            | 
| cs-cz      | Çekçe (Çek Cumhuriyeti)     | 
| da-dk      | Danca (Danimarka)           | 
| de-de      | Almanca (Almanya)           | 
| el-gr      | Yunanca (Yunanistan)             | 
| en-Us      | İngilizce (Amerika Birleşik Devletleri)    | 
| es-es      | İspanyolca (Kastilya)        | 
| et-ee      | Estonca (Estonya)         | 
| eu-es      | Bask dili (İspanya)             | 
| fi-fi      | Fince (Finlandiya)          | 
| fr-fr      | Fransızca (Fransa)            | 
| gl-es      | Galiçya dili (İspanya)           | 
| hi-HU      | Macarca (Macaristan)        | 
| hi-in      | Hintçe (Hindistan)              | 
| hr-hr      | Hırvatça (Hırvatistan)         | 
| id-Id      | Endonezce (Endonezya)     | 
| it-It      | İtalyanca (İtalya)            | 
| jp-Jp      | Japonca (Japonya)           | 
| kk-kz      | Kazakça (Kazakistan)        | 
| ko-kr      | Korece (Kore)             | 
| lt-LT      | Litvanca (Litvanya)     | 
| lv-lv      | Letonca (Letonya)           | 
| ms-my      | Malayca (Malezya)           | 
| nb-no      | Norveççe (Bokmål)         | 
| nl-nl      | Felemenkçe (Hollanda)        | 
| pl-pl      | Lehçe (Polonya)            | 
| pt-br      | Portekizce (Brezilya)        | 
| pt-pt      | Portekizce (Portekiz)      | 
| ro-ro      | Rumence (Romanya)         | 
| ru-ru      | Rusça (Rusya)           | 
| sk-sk      | Slovakça (Slovakya)          | 
| sl-si      | Slovence (Slovenya)       | 
| sr-cyrl-rs | Sırpça (Kiril, Sırbistan) | 
| sr-latn-rs | Sırpça (Latin, Sırbistan)    | 
| sv-se      | İsveççe (İsveç)           | 
| th-th      | Tayca (Tayland)            | 
| tr-tr      | Türkçe (Türkiye)           | 
| uk-ua      | Ukraynaca (Ukrayna)        | 
| vi-vn      | Vietnamca (Vietnam)      |
