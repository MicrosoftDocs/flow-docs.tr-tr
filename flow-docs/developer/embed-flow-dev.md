---
title: Microsoft Flow web siteleri ve uygulamalarla tümleştirin | Microsoft Docs
description: Microsoft Flow deneyimlerini Web sitenize veya uygulamanıza ekleyin.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: cf2f14826670cf221411fa2204ee9b2c5581222e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547721"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Microsoft Flow web siteleri ve uygulamalarla tümleştirin
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Kullanıcılarınıza kişisel veya profesyonel görevlerini otomatik hale getirmek için basit bir yol sağlamak üzere *akış pencere* öğelerini kullanarak uygulamanıza veya web sitenize Microsoft Flow ekleyin.

Akış pencere öğeleri, bir konak belgesinde yer alan iframe 'lardır. Bu belge Microsoft Flow tasarımcısında bir sayfaya işaret eder. Bu pencere öğeleri, belirli Microsoft Flow işlevselliğini üçüncü taraf uygulamayla tümleştirir.

Pencere öğeleri basit olabilir. Örneğin, ana bilgisayar ve iframe arasında iletişimi olmayan şablonların bir listesini oluşturan bir pencere öğesi. Pencere öğeleri de karmaşık olabilir. Örneğin, bir şablondan akış sağlayan ve ardından ana bilgisayar ve pencere öğesi arasında iki yönlü iletişim aracılığıyla akışı tetikleyen bir pencere öğesi.

## <a name="prerequisites"></a>Kaynakları

- Bir **Microsoft hesabı** veya
- Bir iş veya okul hesabı

## <a name="use-the-unauthenticated-widget"></a>Kimliği doğrulanmamış pencere öğesini kullan
Kimliği doğrulanmamış şablonlar pencere öğesini kullanmak için, bir iframe kullanarak doğrudan konak uygulamasına ekleyin. JS SDK veya erişim belirtecine ihtiyacınız yoktur. 

### <a name="show-templates-for-your-scenarios"></a>Senaryolarınız için şablonları gösterme
Başlamak için, Web sitenizde Microsoft Flow şablonları göstermek üzere bu kodu ekleyin:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| parametresinin | Açıklaması |
| --- | --- |
| ayarlar |Şablon görünümü için dört harfli dil ve bölge kodu. Örneğin, `en-us` Amerikan Ingilizce 'yi temsil eder ve `de-de` Almanca 'yı temsil eder. |
| arama terimi |Görünümde göstermek istediğiniz şablonların arama terimi. Örneğin, Wunderlist şablonlarını göstermek için `wunderlist` aratın. |
| şablon sayısı |Görünümde göstermek istediğiniz şablon sayısı. |
| Hedefine |Kullanıcılar şablonu seçerken açılan sayfa. Şablonla ilgili ayrıntıları göstermek için `details` girin veya Microsoft Flow tasarımcısını açmak için `new` girin. |
| alan |Verilen şablon kategorisine filtreler. | 
| parametrelere. ada |Akışa geçirilecek ek bağlam. |


Hedef parametre `new`, kullanıcılar bir şablon seçerken Microsoft Flow tasarımcı açılır. Kullanıcılar daha sonra Tasarımcıda bir akış oluşturabilir. Pencere öğesinde tam deneyimin olmasını istiyorsanız sonraki bölüme bakın.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Akış şablonuna ek parametreler geçirme

Kullanıcı Web sitenizde veya uygulamanızda belirli bir bağlamda yer alıyorsa, bu bağlamı akışa geçirmek isteyebilirsiniz. Örneğin, bir Kullanıcı bir *listeye bir öğe eklendiğinde* , Wunderlist 'te belirli bir listeye bakarken bana bir şablon açabilir. Liste KIMLIĞINI akışa *parametre* olarak geçirmek için şu adımları izleyin:

1. Bir parametreyi yayımlamadan önce akış şablonunda tanımlayın. Bir parametre `@{parameters('parameter_name')}`gibi görünür.
1. Parametreyi iframe src 'nin sorgu dizesinde geçirin. Örneğin, " **" adlı bir**parametreye sahipseniz `&parameters.listName={the name of the list}` ekleyin.

### <a name="full-sample"></a>Tam örnek

Almanya 'da ilk dört Wunderlist şablonunu göstermek ve kullanıcıyı **Mycoollist**ile başlatmak için şu kodu kullanın:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Kimliği doğrulanmış akış pencere öğelerini kullanma

Aşağıdaki tabloda, Kullanıcı kimlik doğrulaması erişim belirtecini kullanarak pencere öğesi içindeki tam deneyimi destekleyen Microsoft Flow Pencere öğelerinin listesi gösterilmektedir. Pencere öğelerini eklemek ve gerekli Kullanıcı erişim belirtecini sağlamak için Microsoft Flow JavaScript yazılım geliştirici seti 'ni (JS SDK) kullanmanız gerekir.

| Pencere öğesi türü    | Desteklenen özellik                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Var          | Kişisel ve paylaşılan akışlar için bir sekmedeki akışların listesini gösterir. Mevcut bir akışı düzenleyin veya bir şablondan veya boş olarak yeni bir akış oluşturun. | 
| Flowoluşturma   | Ana bilgisayar uygulamasının sağladığı şablon kimliğinden bir akış oluşturur.                                                                | 
| çalışma zamanı        | Ana bilgisayar uygulamasının sağladığı bir el ile veya karma tetikleme akışını tetikler.                                                        | 
| approvalCenter | Onay isteklerini ve gönderilen onayları gömer.                                                                                        | 
| şablondan      | Şablonların listesini gösterir. Kullanıcı yeni bir akış oluşturmak için bir tane seçer.                                                                         | 

Kullanıcıların doğrudan Web siteniz veya uygulamanızdan akış oluşturmalarına ve yönetmesine izin vermek için kimliği doğrulanmış akış SDK 'sını kullanın (Microsoft Flow gezinmek yerine). Kimliği doğrulanmış SDK 'Yı kullanmak için kullanıcıyı Microsoft hesabıyla veya Azure Active Directory oturum açmanız gerekir.

> [!NOTE]
> Pencere öğeleri kullanırken Microsoft Flow markalamayı gizlemenin bir yolu yoktur.

## <a name="widget-architecture"></a>pencere öğesi mimarisi

Microsoft Flow pencere öğeleri, bir konak uygulamasına Microsoft Flow başvuran bir iframe katıştırarak çalışır. Ana bilgisayar Microsoft Flow pencere öğesi için gereken erişim belirtecini sağlar. Microsoft Flow JS SDK 'Sı, ana bilgisayar uygulamasının pencere öğesi yaşam döngüsünü başlatmasını ve yönetmesini sağlar.

![pencere öğesi mimarisi](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>JS SDK ayrıntıları

Microsoft Flow ekibi, üçüncü taraf uygulamalarda akış Pencere öğelerinin tümleştirilmesine yardımcı olmak için JS SDK 'sını sağlar. Flow JS SDK 'Sı, Flow hizmetinde ortak bir bağlantı olarak kullanılabilir ve konak uygulamanın pencere öğesi üzerindeki olayları işlemesini ve pencere öğesine eylemler göndererek akış uygulamasıyla etkileşime geçmesini sağlar. Pencere öğesi olayları ve eylemleri pencere öğesi türüne özeldir.

### <a name="widget-initialization"></a>Pencere öğesi başlatma

Pencere öğesi başlatılmadan önce Flow JS SDK başvurusunun konak uygulamasına eklenmesi gerekir.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Bir JSON nesnesinde isteğe bağlı konak adı ve yerel ayar değerlerini geçirerek bir JS SDK örneği oluşturun.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| Ada     | Gerekli/Isteğe bağlı | Açıklaması                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Seçim          | Microsoft Flow ana bilgisayar adı, örneğin https://flow.microsoft.com        | 
| `locale`   | Seçim          | Pencere öğesinin istemci yerel ayarı (belirtilmemişse `en-Us` varsayılan olarak) | 


JS SDK örneği oluşturulduktan sonra konak uygulamasındaki üst öğe içinde bir Microsoft Flow pencere öğesi başlatabilir ve ekleyebilirsiniz. Bunu yapmak için bir HTML div ekleyin:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Sonra, Microsoft Flow pencere öğesini JS SDK `renderWidget()` yöntemiyle başlatın. Pencere öğesi türünü ve bunlara karşılık gelen ayarları sağladığınızdan emin olun.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

Burada, ana bilgisayar uygulamasının boyutlarıyla eşleşecek şekilde değiştirebileceğiniz kapsayıcı için örnek bir stil verilmiştir.

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

`renderWidget()`için parametreler şunlardır: 

| parametresinin        | Gerekli/Isteğe bağlı | Açıklaması                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Gerekli          | Pencere öğesinin katıştırılacağı konak sayfasındaki DIV öğesinin kimliği.                   | 
| `environmentId`    | Seçim          | Pencere öğelerinin bir ortam kimliği olması gerekir. Bir kimlik sağlamazsanız, varsayılan bir ortam kullanılır. | 
| `flowsSettings`    | Seçim          | Microsoft Flow Settings nesnesi                                                                        | 
| `templateSettings` | Seçim          | Şablon Ayarları nesnesi                                                                    | 
| `approvalSettings` | Seçim          | Onay Ayarları nesnesi                                                                    | 

### <a name="access-tokens"></a>Erişim belirteçleri

JS SDK `renderWidget()` çalıştıktan sonra, JS SDK, Microsoft Flow pencere öğesi URL 'sine işaret eden bir IFRAME başlatır. Bu URL, sorgu dizesi parametrelerinin tüm ayarlarını içerir. Konak uygulamasının, pencere öğesini başlatılmadan önce Kullanıcı için bir Microsoft Flow erişim belirteci alması gerekir (hedef kitle https://service.flow.microsoft.com) Azure Active Directory JWT belirteci. Pencere öğesi, konaktan bir erişim belirteci istemek için `GET_ACCESS_TOKEN` bir olay oluşturur. Konağın olayı işlemesi ve belirteci pencere öğesine geçirmesi gerekir:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

Ana bilgisayar uygulaması, belirtecin korunmasından ve istendiği sırada pencere öğesine geçerli bir süre sonu tarihiyle geçirilmesinden sorumludur. Pencere öğesi daha uzun süreler için açıksa, ana bilgisayar belirtecin süresi dolup dolduğunu denetlemelidir ve onu pencere öğesine geçirmeden önce gerekliyse belirteci yenileyebilir.

### <a name="detecting-if-the-widget-is-ready"></a>Pencere öğesinin Ready olup olmadığı algılanıyor

Başlatma başarılı olduktan sonra pencere öğesi, pencere öğesinin kullanıma hazırlanmasının olduğunu bildirmek için bir olay oluşturur. Ana bilgisayar `WIDGET_READY` olayını dinleyebilir ve ek ana bilgisayar kodu yürütebilir.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Pencere öğesi ayarları

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings, Microsoft Flow pencere öğesinin işlevlerini özelleştirmek için kullanılabilir.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| parametresinin | Gerekli/Isteğe bağlı | Açıklaması | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Gerekli | Kullanıcı akış pencere öğesinde **boş oluştur** düğmesini seçtiğinde şablonun GUID 'ini kullanın | 
| `flowsFilter` | Seçim | Microsoft Flow pencere öğesi, akışlar listelenirken belirtilen filtreyi uygular. Örneğin, belirli bir SharePoint sitesine başvuran akışları gösterin. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Seçim | Microsoft Flow pencere öğesinde göstermek için etkin sekmesini varsayılan olarak belirler. <br /> Örneğin, <br /> Takım sekmesini ```tab:'sharedFlows' ``` görüntüler<br /> ve ``` tab:'myFlows' ``` Akışlarım sekmesini görüntüler. |   

### <a name="templatessettings"></a>Templates ayarları 

Bu, akışlar, Flowoluşturma ve şablonlar pencere öğeleri gibi bir şablondan akış oluşturmanıza olanak sağlayan tüm pencere öğeleri için geçerlidir.

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

| parametresinin |Gerekli/Isteğe bağlı | Açıklaması                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Seçim          | Şablondan akış oluştururken kullanılacak tasarım zamanı parametreleri, örneğin: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Seçim          | Geçerli değerler ' New ' veya ' details '. ' Details ' olarak ayarlandığında, bir şablondan akış oluştururken bir ayrıntı sayfası gösterilir.     |
| `pageSize` | Seçim          | Görüntülenecek şablon sayısı. Varsayılan boyut = 6 | 
| `searchTerm` | Seçim          | Belirtilen arama terimiyle eşleşen şablonları görüntüle| 
| `templateCategory` | Seçim          | Belirli bir kategoride şablonları görüntüleme| 
 
### <a name="approvalcentersettings"></a>Approvalcenterayarları

ApprovalCenter pencere öğeleri için geçerlidir.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| parametresinin | Gerekli/Isteğe bağlı | Açıklaması | 
|------------|-------------------|--------------| 
| `hideLink`| Seçim | `true`olarak ayarlandığında pencere öğesi alındı ve gönderilen onay bağlantılarını gizler | 
| `autoNavigateToDetails`| Seçim | `true`olarak ayarlandığında pencere öğesi yalnızca bir onay mevcut olduğunda onay ayrıntılarını otomatik olarak açar | 
| `approvalsFilter`| Seçim | Onay pencere öğesi onayları listelerken belirtilen onay filtresini uygular, örneğin: onay pencere öğesi onayları listelerken belirtilen onay filtresini uygular, örneğin: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Seçim | Akış pencere öğesinde gösterilecek varsayılan etkin sekme. <br/> Geçerli değerler: ' Receivedapproışları ', ' Sentapproışları ' | 
| `showSimpleEmptyPage`| Seçim | Onay olmadığında boş bir sayfa gösterir | 
| `hideInfoPaneCloseButton` | Seçim | Bilgi bölmesi kapatma düğmesini gizler (veya konağın zaten bir kapatma düğmesi var) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Pencere öğesi olayları

Microsoft Flow pencere öğesi, ana bilgisayarın yaşam döngüsü olaylarını bir şekilde dinlemesine olanak sağlayan olayları destekler. Microsoft Flow pencere öğesi iki tür olayı destekler: tek yönlü bildirim olayları (örneğin, pencere öğesi\_için) ve konaktan veri getirmek için pencere öğesinden oluşturulan olaylar (\_erişim\_belirteci). Konağın pencere öğesinde oluşturulan belirli olayları dinlemek için pencere öğesi. listen () yöntemini kullanması gerekir.

### <a name="usage"></a>Kullanımıyla

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Pencere öğesi türüne göre desteklenen olaylar

| Pencere öğesi olayı      | Bilgileri                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Pencere öğesi başarıyla yüklendi                                      | 
| `WIDGET_RENDERED`   | Pencere öğesi yüklendi ve Kullanıcı arabirimi işleme tamamlanmıştır                      | 
| `GET_ACCESS_TOKEN`  | Kullanıcı erişim belirteci ekleme için pencere öğesi isteği                      | 
| `GET_STRINGS`       | Konağın pencere öğesinde gösterilen UI dizeleri kümesini geçersiz kılmasına izin verir | 

### <a name="runtime-widget"></a>Çalışma zamanı pencere öğesi

| Pencere öğesi olayı                    | Bilgileri                                     | Verileri                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Tetiklendi ve Flow çalıştırması başlatıldı      |           | 
| `RUN_FLOW_COMPLETED`              | Akış çalıştırması başarıyla tetiklendi             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | Akış çalıştırmasında Kullanıcı tarafından seçilen bitti düğmesi       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Kullanıcı akış çalıştırmasında Iptal düğmesini seçti     |           | 
| `FLOW_CREATION_SUCCEEDED`         | Akış başarıyla oluşturuldu           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Ana bilgisayar pencere öğesini kapatması gerektiğinde tetiklenir |       | 

### <a name="flow-creation-widget"></a>Akış oluşturma pencere öğesi

| Pencere öğesi olayı             | Bilgileri                                  | Verileri  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Akış oluşturma başarısız oldu                     |       | 
| `WIDGET_CLOSE`             | Konağın pencere öğesini kapatması gerektiğinde harekete geçirildi  |       | 
| `TEMPLATE_LOAD_FAILED`     | Şablon yüklenemedi              |       | 
| `FLOW_CREATION_SUCCEEDED`  | Akış başarıyla oluşturuldu        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Onay pencere öğesi

| Pencere öğesi olayı                      | Bilgileri                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Alınan onay durumu değiştirildi  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Gönderilen onay durumu değiştirildi      | 

**\_dizeleri al** olayı, pencere öğesinde gösterilen bazı Kullanıcı arabirimi öğeleri için metin özelleştirmenize olanak sağlar. Aşağıdaki dizeler özelleştirilebilir:

| Dize anahtarı                     | Pencere öğesinde kullan                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Akış oluşturma düğmesinde hem akış oluşturma hem de çalışma zamanı pencere öğesinde görünen metin                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | Akış oluşturma pencere öğesinde akış adı için kullanılacak başlangıç değeri. Yalnızca allowCustomFlowName ayarı etkinleştirildiğinde kullanılır. | 
| `FLOW_CREATION_HEADER`           | Akış oluşturma ve çalışma zamanı pencere öğesinde akış oluştururken kullanılacak üst bilgi                                                    | 
| `INVOKE_FLOW_HEADER`             | Çalışma zamanı pencere öğesinde bir akış çağrılırken kullanılacak üst bilgi                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Çalışma zamanı pencere öğesinde bir akışı çağırmak/çalıştırmak için kullanılan düğme üzerinde görünen metin                                                       | 

### <a name="example"></a>Örneğinde

Varsayılan değeri geçersiz kılmak için anahtar-değer çiftleri ile bir JSON nesnesi geçirerek çağırın `widgetDoneCallback`.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Pencere öğesi eylemleri

Konak, pencere öğesine belirli bir eylem veya ileti göndermek için pencere öğesi eylemlerini kullanır. Pencere öğesi JS SDK 'Sı, bir ileti veya JSON yükünü pencere öğesine göndermek için `notify()` yöntemi sağlar. Her pencere öğesi eylemi belirli bir yük imzasını destekler.

### <a name="usage"></a>Kullanımıyla

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Örneğinde 

Bir çalışma zamanı pencere öğesine aşağıdaki komutu göndererek bir akış çağırın 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Çalışma zamanı pencere öğesi

| Pencere öğesi eylemi                               | Bilgileri                                                      | Parametre arabirimi  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Akış çalıştırmasını tetikler                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Şablon tarafından çalıştırılan akışı tetikler                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Akış için tetikleyici şemasını alır                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Bekleyen etkinlikleri iptal eder ve bir WIDGET_CLOSE olayı başlatır |                      | 

### <a name="flow-creation-widget"></a>Akış oluşturma pencere öğesi

| Pencere öğesi eylemi                               | Bilgileri                                                      | Parametre arabirimi  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Seçili şablon için bir akış oluşturur                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Seçili şablon tanımı için bir akış oluşturur          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Bekleyen etkinlikleri iptal eder ve bir WIDGET_CLOSE olayı başlatır |                      | 

### <a name="approval-widget"></a>Onay pencere öğesi

| Pencere öğesi eylemi  | Bilgileri                                           | Parametre arabirimi  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Onay ayrıntılarını görüntüleyen bilgi bölmesini kapatır  | yok                  | 

## <a name="configuring-your-client-application"></a>İstemci uygulamanızı yapılandırma

İstemci uygulamanızı Flow hizmeti kapsamları (temsilci Izinleri) ile yapılandırmanız gerekir. Pencere öğesi tümleştirmesi için kullanılan Azure Active Directory (AAD) uygulaması ' kod verme ' yetkilendirme akışı kullanıyorsa, AAD uygulamasının Microsoft Flow tarafından desteklenen temsilci izinleri ile önceden yapılandırılmış olması gerekir. Bu, uygulamaya izin veren temsilci izinleri sağlar:

-   Onayları Yönet
-   Onayları oku
-   Etkinlikleri okuyun
-   Akışları Yönet
-   Akışları oku

Bir veya daha fazla temsilci izni seçmek için şu adımları izleyin:

1.  https://portal.azure.com git 
2.  **Azure Active Directory**seçin.
3.  **Yönet**altında **uygulama kayıtları** seçin.
4.  Flow hizmeti kapsamları için yapılandırılacak üçüncü taraf uygulamayı girin.
5.  **Ayarlar**' ı seçin.
      ![pencere öğesi mimarisi](../media/embed-flow-dev/AAD-App-Settings.png)
6. **API erişimi** altında **gerekli izinleri** seçin/
7. **Ekle**' yi seçin.
8. **BIR API seçin**öğesini seçin.
      ![pencere öğesi mimarisi](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. **Microsoft Flow hizmeti** araması yapın ve seçin. Note: Microsoft Flow hizmeti görebilmeniz için, kiracınızın Flow portalında (<https://flow.microsoft.com>) en az bir AAD kullanıcısının oturum açması gerekir
10. Uygulamanız için gerekli akış kapsamlarını seçin ve ardından **Kaydet**' i seçin.
      ![pencere öğesi mimarisi](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Uygulamanız artık JWT belirtecindeki \'SCP ' talebinde temsilci izinleri içeren bir akış hizmeti belirteci alacak.

## <a name="sample-application-embedding-flow-widgets"></a>Örnek uygulama katıştırma akış pencere öğeleri 

Kaynaklar bölümünde örnek bir JavaScript tek sayfalı uygulama (SPA) sağlanır. bu sayede akış pencere öğelerini bir konak sayfasına katıştırmayı deneyebilirsiniz. Örnek uygulamanın kullanılması için örtük izin akışı etkinleştirilmiş bir AAD uygulamasının kaydedilmesi gerekir.

### <a name="registering-an-aad-app"></a>AAD uygulaması kaydetme

1.  [Azure Portal](https://portal.azure.com/)oturum açın.
2.  Sol gezinti bölmesinde **Azure Active Directory**' yi seçin ve sonra yeni kayıt \> **uygulama kayıtları** (Önizleme) öğesini seçin.
3.  **Bir uygulamayı kaydet** sayfası göründüğünde, uygulamanız için bir ad girin.
4.  **Desteklenen hesap türleri**altında, herhangi bir kuruluş dizininde **hesaplar** ' ı seçin.
5.  **Yeniden yönlendirme URL 'si** bölümünde Web platformu ' nu seçin ve değeri Web sunucunuza göre uygulama\'s URL 'si olarak ayarlayın.  Örnek uygulamayı çalıştırmak için bu değeri http://localhost:30662/ olarak yapılandırın.
6.  **Kaydol**' u seçin.
7.  Uygulamaya **genel bakış** sayfasında, uygulama (ISTEMCI) kimliği değerini aklınızda edin.
8.  Örnek, [örtük verme akışının](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) etkinleştirilmesini gerektirir. Kayıtlı uygulamanın sol gezinti bölmesinde **kimlik doğrulaması**' nı seçin.
9.  **Gelişmiş ayarlar**' da, **örtük izin**' ın altında, **kimlik belirteçlerini** ve **erişim belirteçleri** onay kutularını etkinleştirin. Bu uygulamanın kullanıcılar oturum açması ve Flow API çağrısı yapması gerektiğinden, KIMLIK belirteçleri ve erişim belirteçleri gereklidir.
10. **Kaydet**' i seçin.

### <a name="running-the-sample"></a>Örnek çalıştırma
<!-- todo where should I download from? -->
1.  Örneği indirin ve cihazınızdaki yerel bir klasöre kopyalayın.
2.  FlowSDKSample klasörünün altında index. html dosyasını açın ve `clientID` daha önce kaydettiğiniz uygulama KIMLIĞINE güncelleştirmek için `applicationConfig` değiştirin.
    ![pencere öğesi mimarisi](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  Örnek uygulama, akış kapsamları akışlarını kullanacak şekilde yapılandırılmıştır **. Read. All** ve **Flow. Manage. ALL.** **Applicationconfig** nesnesindeki **flowscopes** özelliğini güncelleştirerek ek kapsamları yapılandırabilirsiniz.
4.  Bağımlılığı yüklemek ve örnek uygulamayı çalıştırmak için şu komutları çalıştırın:
    > \> NPM install \> node Server. js
5. Tarayıcıyı açın ve ardından http://localhost:30662 girin
6. AAD 'de kimlik doğrulaması yapmak ve bir akış erişim belirteci almak için **oturum aç** düğmesini seçin.
7. Erişim **belirteci** metin kutusu erişim belirtecini içerir.
    ![pencere öğesi mimarisi](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. İlgili pencere öğelerini eklemek için **akışları Yükle pencere öğesini** veya **şablon Yükle pencere öğesini** seçin.
    ![pencere öğesi mimarisi](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

Örnek uygulama [indirme bağlantısı](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip).

## <a name="resources"></a>Kaynakların

### <a name="widget-test-pages"></a>Pencere öğesi test sayfaları

Pencere öğesi tümleştirme ve ayarları hakkında daha fazla bilgi edinin:

- Şablonlar pencere öğesi: <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- Flowoluşturma pencere öğesi: <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- Çalışma zamanı pencere öğesi: <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- Onaylar Merkezi pencere öğesi: <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- Akışlar pencere öğesi: <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>Desteklenen pencere öğesi yerel ayarları

Başlatılmış yerel ayar listelenmiyorsa, akış varsayılan olarak en yakın desteklenen yerel ayara sahip olur.

| ayarlar     | Dildir                   | 
|------------|----------------------------| 
| bg-bg      | Bulgarca (Bulgaristan)       | 
| ca-es      | Katalanca (Ispanya)            | 
| CS-CZ      | Çekçe (Çek Cumhuriyeti)     | 
| da-dk      | Danca (Danimarka)           | 
| De-de      | Almanca (Almanya)           | 
| el-gr      | Yunanca (Yunanistan)             | 
| en-US      | İngilizce (Birleşik Devletler)    | 
| Es-es      | İspanyolca (CAStilian)        | 
| et-Ee      | Estonya dili (Estonya)         | 
| AB-es      | Bask dili (Ispanya)             | 
| Fi-Fi      | Fince (Finlandiya)          | 
| Fr-fr      | Fransızca (Fransa)            | 
| GL-ES      | Galicia (Ispanya)           | 
| Merhaba-HU      | Macarca (Macaristan)        | 
| Merhaba      | Hintçe (Hindistan)              | 
| HR-SA      | Hırvatça (Hırvatistan)         | 
| kimlik kimliği      | Endonezya dili (Endonezya)     | 
| BT BT      | İtalyanca (Italya)            | 
| JP-JP      | Japonca (Japonya)           | 
| kk-KZ      | Kazakça (Kazakistan)        | 
| Ko-KR      | Kore dili (Kore)             | 
| lt-LT      | Litvanca (Litvanya)     | 
| LV-LV      | Letonca (Letonya)           | 
| MS-My      | Malay dili (Malezya)           | 
| NB-hayır      | Norveççe (Bokmål)         | 
| nl-nl      | Hollanda dili (Hollanda)        | 
| Pl-pl      | Lehçe (Polonya)            | 
| Pt-br      | Portekizce (Brezilya)        | 
| PT NK      | Portekizce (Portekiz)      | 
| Ro-Ro      | Rumence (Romanya)         | 
| Ru-ru      | Rusça (Rusya)           | 
| SK-SK      | Slovakça (Slovakya)          | 
| SL-si      | Slovence (Slovenya)       | 
| SR-Cyrl-RS | Sırpça (Kiril, Sırbistan) | 
| sr-Latn-RS | Sırpça (Latin, Sırbistan)    | 
| ZF-s      | İsveççe (Isveç)           | 
| TH-TH      | Tay dili (Tayland)            | 
| Tr-tr      | Türkçe (Türkiye)           | 
| UK-UA      | Ukrayna dili (Ukrayna)        | 
| vi-VN      | Vietnam dili (Viet Nam)      |
