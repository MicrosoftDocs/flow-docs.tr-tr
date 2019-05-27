---
title: Limitler ve yapılandırma | Microsoft Docs
description: Limitler ve yapılandırma
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/04/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 615d13adaee8b5db302065b3c21a488504f39398
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64906412"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Microsoft Flow’da limitler ve yapılandırma
Bu konu, akışlara yönelik geçerli limitler ve yapılandırma ayrıntılarıyla ilgili bilgi içerir.

## <a name="request-limits"></a>İstek limitleri
Bunlar tek bir giden isteğe yönelik limitlerdir.

### <a name="timeout"></a>Zaman aşımı

| Ad | Limit |
| --- | --- |
| Zaman uyumlu çağrılar için İstek Zaman Aşımı |120 Saniye |
| Zaman uyumsuz çağrılar için İstek Zaman Aşımı|Yapılandırılabilir. En fazla 30 gündür. |

### <a name="message-size"></a>İleti boyutu

| Ad | Limit | Notlar |
| --- | --- | --- |
| İleti boyutu |100 MB |API’lerden bazıları 100 MB’ın tamamını desteklenmez. |
| İfade değerlendirme limiti |131.072 karakter |`@concat()`, `@base64()`, `string` bu sınırı aşamaz. |

### <a name="retry-policy"></a>Yeniden deneme ilkesi

| Ad | Limit |
| --- | --- |
| Yeniden deneme sayısı |90 | Varsayılan değer 4'tür. Varsayılan değeri değiştirmek için eylem ayarlarını kullanın | 
| En fazla gecikmede yeniden dene |1 gün | |
| Yeniden deneme en az gecikme süresi |5 saniye | |

## <a name="run-duration-and-retention"></a>Çalışma süresi ve bekletme
Bunlar tek bir akış çalıştırmasına yönelik limitlerdir.

| Ad | Limit | Notlar |
| --- | --- | --- |
| Çalıştırma süresi |30 gün |Onaylar gibi bekleyen adımları olan iş akışlarını içerir. 30 gün geçtikten sonra bekleyen adımlar zaman aşımına uğrar. Zaman aşımına uğrayan onaylar, onay merkezinden kaldırılır. Birisi zaman aşımına uğramış bir isteği onaylamaya çalışırsa bir hata iletisi alır. |
| Depolama bekletme |30 gün |Bu, çalıştırma başlangıç saatinden itibaren hesaplanır. |
| En az yinelenme aralığı |1 dakika | |
| En fazla yinelenme aralığı |500 gün | |
| Maksimum çalıştırma geçmişini saklama |GDPR kuralları uyarınca 28 gündür. | |
|En kısa erteleme aralığı - Ücretsiz ve Plan 1 lisansı|5 saniye||
|En kısa erteleme aralığı - Plan 2 lisansı|1 saniye||

## <a name="looping-and-debatching-limits"></a>Döngü ve toplu iş ayırma limitleri
Bunlar tek bir akış çalıştırmasına yönelik limitlerdir.

| Ad | Limit | Notlar |
| --- | --- | --- |
| Her öğeye uygulama - Ücretsiz lisans|5,000 |Gerektiğinde daha büyük dizileri filtrelemek için filtreleme eylemini kullanabilirsiniz. |
| Her öğeye uygulama - Plan 1 ve Plan 2 lisansı|100.000 |Gerektiğinde daha büyük dizileri filtrelemek için filtreleme eylemini kullanabilirsiniz. |
| Yinelemelere kadar |5,000 | |
| SplitOn öğeleri - Ücretsiz lisans |5,000 ||
| SplitOn öğeleri - Plan 1 ve Plan 2 lisansı |100.000 ||
| Her birine uygula Paralellik |50 |Varsayılan olarak döngüler birbiri ardına çalışır (aslına bakılırsa parallellik 1). Varsayılan olarak 50’ye kadar paralel akış yapılandırabilirsiniz. |
| Eylem yürütme işlemleri 5 dakikada bir - Ücretsiz ve Plan 1 lisansı | 2.000 | Ayrıca, bir iş yükünü gerektiğinde birden fazla akış oluşturmak üzere dağıtabilirsiniz. |
|Eylem yürütme işlemleri 5 dakikada bir - Plan 2 lisansı|100.000|Ayrıca, bir iş yükünü gerektiğinde birden fazla akış oluşturmak üzere dağıtabilirsiniz.|
| Eylemler eş zamanlı giden çağrılar - Ücretsiz ve Plan 1 lisansı | ~500 | Eş zamanlı istek sayısını veya süreyi gerektiği gibi azaltın. |
| Eylemler eş zamanlı giden çağrılar - Ücretsiz ve Plan 1 lisansı | Yaklaşık 2.500 | Eş zamanlı istek sayısını veya süreyi gerektiği gibi azaltın. | 

## <a name="throughput-limits"></a>İşleme sınırları

|Ad|Limit|Notlar|
|---|---|---|
|Çalışma zamanı uç noktası - 5 dakikada bir izin verilen okuma çağrısı sayısı - Ücretsiz ve Plan 1 lisansı|6.000||
|Çalışma zamanı uç noktası - 5 dakikada bir izin verilen okuma çağrısı sayısı - Plan 2 lisansı|60.000||
|Çalışma zamanı uç noktası: 5 dakikada bir Invoke çağrıları - Ücretsiz ve Plan 1 lisansı|4.500||
|Çalışma zamanı uç noktası: 5 dakikada bir yapılan Invoke çağrısı sayısı - Plan 2 lisansı|45.000||
|5 dakikada bir izin verilen işleme miktarı - Ücretsiz ve Plan 1 lisansı|600 MB||
|5 dakikada bir izin veline işleme miktarı - Plan 2 lisansı|6 GB||
|Bir saatte oluşturulmasına izin verilen içerik akışı miktarı (eylem girişi/çıkışı) - Ücretsiz, Plan 1 ve Plan 2 lisansı|200 GB||


## <a name="definition-limits"></a>Tanım limitleri
Bunlar tek bir akışa yönelik limitlerdir.

| Ad | Limit | Notlar |
| --- | --- | --- |
| İş akışı başına eylemler |250 |Gerektiğinde bunu genişletmek için iç içe iş akışları ekleyebilirsiniz. |
| İzin verilen eylem iç içe geçme derinliği |5 |Gerektiğinde bunu genişletmek için iç içe iş akışları ekleyebilirsiniz. |
| İfade başına en fazla karakter |8,192 | |
| `action`/`trigger` ad limiti |80 | |
| `description` uzunluk limiti |256 | |

## <a name="sharepoint-limits"></a>SharePoint limitleri
Microsoft SharePoint’i Microsoft Flow ve PowerApps ile nasıl kullanabileceğinize ilişkin [sınırlamalar](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) bulunur.

## <a name="ip-address-configuration"></a>IP adresi yapılandırması
Microsoft Flow isteklerinin hangi IP adresinden gönderileceği, akışı içeren [ortamın](environments-overview-admin.md) bulunduğu [bölgeye](regions-overview.md) bağlıdır. Şu anda akış senaryoları için kullanılabilir FQDN’ler yayımlanmamaktadır.

>[!IMPORTANT]
> Akışın yaptığı bazı çağrılar [Mantıksal uygulamalar](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) belgelerinde listelenen IP adreslerinden gelir. Bu çağrılara örnek olarak HTTP ya da HTTP + OpenAPI verilebilir.

### <a name="logic-apps"></a>Logic Apps
Bir akıştan yapılan çağrılar doğrudan Azure Logic Apps hizmetine gider. Bu çağrılara örnek olarak HTTP ya da HTTP + OpenAPI verilebilir. Bu hizmet tarafından hangi IP adreslerinin kullanıldığını öğrenmek için lütfen [Logic Apps belgelerine](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) bakın.

### <a name="connectors"></a>Bağlayıcılar
Akış içinde (örneğin, SQP API veya SharePoint API) bir bağlayıcıdan yapılan çağrılar burada listelenen IP adreslerinden gelir:

| Bölge | Giden IP |
| --- | --- |
| Asya Pasifik | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Avustralya  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Kanada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Avrupa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| Hindistan  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japonya | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| Güney Amerika | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Birleşik Krallık | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Amerika Birleşik Devletleri | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Önizleme (Amerika Birleşik Devletleri)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Örneğin, Azure SQL veritabanınızın IP adreslerini yetkilendirmeniz gerekiyorsa bu adresleri kullanmanız gerekir.

### <a name="required-services"></a>Gerekli hizmetler
Aşağıdaki tabloda, Microsoft Flow'un bağlandığı hizmetler listelenmiştir. Ağınızda bu hizmetlerden hiçbirinin engellenmediğinden emin olun.

Etki Alanları | Protokoller | Kullanımlar
--------|  ---------| -----
management.azure.com|https|Azure Resource Manager'a erişim.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Active Directory Kimlik Doğrulama Kitaplığı'na (ADAL) erişim.
graph.microsoft.com </br>graph.windows.net</br>|https|Profil fotoğrafı gibi kullanıcı bilgilerinin alınması için Azure AD Graph API'sine erişim.
*.azure-apim.net|https|Bağlayıcılar için Çalışma Zamanına erişim.
*.flow.microsoft.com|https|Microsoft Flow sitesine erişim.
*.powerapps.com|https|PowerApps sitesine erişim.
*.azureedge.net|https|Microsoft Flow CDN erişimi.
nps.onyx.azure.net|https|NPS’ye (Net Promoter Score) erişim.
