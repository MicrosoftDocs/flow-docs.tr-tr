---
title: Sınırlar ve yapılandırma | Microsoft Docs
description: Sınırlar ve yapılandırma
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
ms.date: 05/30/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c6a9b3c344ac25afe90c607b4a665aeaab49321f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547366"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Microsoft Flow sınırları ve yapılandırması
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bu konu, akışlar için geçerli limitlerin ve yapılandırma ayrıntılarının hakkında bilgiler içerir.

## <a name="request-limits"></a>İstek sınırları
Bunlar, tek bir giden istek için sınırlardır.

### <a name="timeout"></a>aş

| Ada | Sınırlı |
| --- | --- |
| Zaman uyumlu çağrılar için istek zaman aşımı |120 saniye |
| Zaman uyumsuz çağrılar için istek zaman aşımı|Yapılandırılabilir. En fazla 30 gündür. |

### <a name="message-size"></a>İleti boyutu

| Ada | Sınırlı | Larını |
| --- | --- | --- |
| İleti boyutu |100 MB |Tüm API 'Ler tam 100MB 'yi desteklemez. |
| İfade değerlendirme sınırı |131.072 karakter |`@concat()`, `@base64()``string` bu sınırı aşamaz. |

### <a name="retry-policy"></a>Yeniden deneme ilkesi

| Ada | Sınırlı |
| --- | --- |
| Yeniden deneme girişimleri |90 | Varsayılan değer 4 ' dir. Varsayılan kullanım eylemi ayarlarını değiştirmek için | 
| Yeniden deneme en fazla gecikme |1 gün | |
| Yeniden deneme en düşük gecikme |5 saniye | |

## <a name="run-duration-and-retention"></a>Çalıştırma süresi ve bekletme
Bunlar tek bir akış çalıştırmasına yönelik limitlerdir.

| Ada | Sınırlı | Larını |
| --- | --- | --- |
| Çalışma süresi |30 gün |Onaylar gibi bekleyen adımlara sahip iş akışlarını içerir. 30 gün sonra, bekleyen adımlar zaman aşımına uğrar. Zaman aşımına uğrayan onaylar, onay merkezinden kaldırılır. Birisi zaman aşımına uğramış bir isteği onaylamayı denerse bir hata mesajı alırlar. |
| Depolama bekletme |30 gün |Bu, çalıştırma başlangıç zamanından itibaren yapılır. |
| En az yinelenme aralığı |1 dakika | |
| En fazla yinelenme aralığı |500 gün | |
| En fazla çalıştırma geçmişi saklama |28 gün, GDPR kuralları başına. | |
|Minimum erteleme aralığı-ücretsiz ve plan 1 lisansı|5 saniye||
|Minimum erteleme aralığı-plan 2 lisansı|1 saniye||

## <a name="looping-and-debatching-limits"></a>Döngü ve toplu işleme limitleri
Bunlar tek bir akış çalıştırmasına yönelik limitlerdir.

| Ada | Sınırlı | Larını |
| --- | --- | --- |
| Her öğeye Uygula-ücretsiz lisans|5\.000 |Gerektiğinde daha büyük dizileri filtrelemek için filtre eylemini kullanabilirsiniz. |
| Her öğe için geçerlidir-plan 1 ve plan 2 lisansı|100.000 |Gerektiğinde daha büyük dizileri filtrelemek için filtre eylemini kullanabilirsiniz. |
| Yinelemeden Until |5\.000 | |
| Spton öğeleri-ücretsiz lisans |5\.000 ||
| Spton öğeleri-plan 1 ve plan 2 lisansı |100.000 ||
| Her paralellik için geçerlidir |50 |Varsayılan olarak, döngüler sırayla çalışır (temelde, paralellik 1 ' dir). Paralel olarak en fazla 50 yapılandırabilirsiniz. |
| 5 dakika başına eylem yürütmeleri – ücretsiz, Office365, plan 1 lisansı ve deneme planları | 2\.000 | Ayrıca, gerektiğinde bir iş yükünü birden fazla akış arasında dağıtabilirsiniz. |
|5 dakika başına eylem yürütmeleri – ücretli plan 2 lisansı|100.000|Ayrıca, gerektiğinde bir iş yükünü birden fazla akış arasında dağıtabilirsiniz.|
|5 dakika başına eylem yürütmeleri – ücretli plan 2 lisansı|150.000|Ayrıca, gerektiğinde bir iş yükünü birden fazla akış arasında dağıtabilirsiniz.|
| Eylemler eşzamanlı giden çağrı-ücretsiz ve plan 1 lisansı | ~ 500 | Eşzamanlı istek sayısını azaltın veya süreyi gerektiği gibi azaltın. |
| 24 saat başına eylem yürütmeleri – ücretsiz, Office365, plan 1 lisansı ve deneme planları | ~ 2.500 | Eşzamanlı istek sayısını azaltın veya süreyi gerektiği gibi azaltın. | 

## <a name="throughput-limits"></a>Verimlilik sınırları

|Ada|Sınırlı|Larını|
|---|---|---|
|Çalışma zamanı uç noktası-5 dakikalık ücretsiz ve plan 1 lisansı başına izin verilen okuma çağrısı sayısı|6\.000||
|Çalışma zamanı uç noktası-5 dakika başına izin verilen okuma çağrısı sayısı-plan 2 lisansı|60.000||
|Çalışma zamanı uç noktası: 5 dakikalık-ücretsiz ve plan 1 lisansı başına çağrı çağırma|4\.500||
|Çalışma zamanı uç noktası: 5 dakika başına çağrı çağrısı sayısı-plan 2 lisansı|45.000||
|5 dakikalık-ücretsiz ve plan 1 lisansı başına izin verilen aktarım hızı miktarı|600 MB||
|5 dakika başına izin verilen üretilen iş miktarı-plan 2 lisansı|6 GB||
|Bir saatlik, plan 1 ve plan 2 lisansı için içerik akışı miktarına (eylem girişleri/çıkışları) üretme izni verilir|200 GB||


## <a name="definition-limits"></a>Tanım sınırları
Bunlar tek bir akışa yönelik limitlerdir.

| Ada | Sınırlı | Larını |
| --- | --- | --- |
| İş akışı başına eylem |250 |Bunu gerektiğinde genişletmek için iç içe geçmiş iş akışları ekleyebilirsiniz. |
| İzin verilen eylem iç içe geçme derinliği |240 |Bunu gerektiğinde genişletmek için iç içe geçmiş iş akışları ekleyebilirsiniz. |
| İfade başına en fazla karakter |8\.192 | |
| `action`/`trigger` ad sınırı |80 | |
| `description` uzunluk sınırı |256 | |

## <a name="sharepoint-limits"></a>SharePoint limitleri
Microsoft SharePoint 'i Microsoft Flow ve PowerApps ile nasıl kullanabileceğinizi gösteren [sınırlamalar](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) vardır.

## <a name="ip-address-configuration"></a>IP adresi yapılandırması
Microsoft Flow isteklerinin gönderildiği IP adresi, akışı içeren [ortamın](environments-overview-admin.md) bulunduğu [bölgeye](regions-overview.md) bağlıdır. Şu anda akış senaryolarında kullanılabilir olan FQDN 'leri yayımlıyoruz.

>[!IMPORTANT]
> Bir akış çağrısı, [Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) BELGELERINDE listelenen IP adreslerinden gelebilir. Bu çağrılara örnek olarak HTTP ya da HTTP + Openapı verilebilir.

### <a name="logic-apps"></a>Logic Apps
Akıştan yapılan çağrılar doğrudan Azure Logic App Service aracılığıyla gider. Bu çağrılara örnek olarak HTTP ya da HTTP + Openapı verilebilir. Lütfen bu hizmet tarafından IP adreslerinin kullanıldığı [Logic Apps belgelerine](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) başvurun.

### <a name="connectors"></a>Larında
Akıştaki bir bağlayıcıdan yapılan çağrılar (örneğin, SQL API 'SI veya SharePoint API 'SI), burada listelenen IP adreslerinden gelir:

| Geli | Giden IP |
| --- | --- |
| Asya Pasifik | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Avustralya  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Kanada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| 'Ya | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| Hindistan  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japonya | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| Güney Amerika | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Birleşik Krallık | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Amerika Birleşik Devletleri | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Önizleme (Birleşik Devletler)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Örneğin, Azure SQL veritabanınızın IP adreslerini yetkilendirmeniz gerekiyorsa, bu adresleri kullanmanız gerekir.

### <a name="required-services"></a>Gerekli hizmetler
Aşağıdaki tabloda Microsoft Flow bağlandığı hizmetler listelenmektedir. Ağınızda bu hizmetlerden hiçbirinin engellenmediğinden emin olun.

etki alanları | Ekledikten | Kullanma
--------|  ---------| -----
management.azure.com|'Dir|Azure Resource Manager erişim.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|'Dir|Active Directory Authentication Library erişimi (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|'Dir|Profil fotoğrafı gibi Kullanıcı bilgilerini almak için Azure AD Graph API erişim.
*. azure-apim.net|'Dir|Bağlayıcılar için çalışma zamanına erişin.
*. flow.microsoft.com|'Dir|Microsoft Flow sitesine erişim.
*. powerapps.com|'Dir|PowerApps sitesine erişim.
*. azureedge.net|'Dir|Microsoft Flow CDN 'ye erişin.
nps.onyx.azure.net|'Dir|NPS erişimi (Net Promoter puanı).
