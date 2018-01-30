---
title: "Limitler ve yapılandırma | Microsoft Docs"
description: "Limitler ve yapılandırma"
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/02/2017
ms.author: stepsic
ms.openlocfilehash: c5fefde9bdd2f8e82052abfaa64a7188d768d8ea
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2018
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Microsoft Flow'da limitler ve yapılandırma
Bu konu, akışlara yönelik geçerli limitler ve yapılandırma ayrıntılarıyla ilgili bilgi içerir.

## <a name="request-limits"></a>İstek limitleri
Bunlar tek bir giden isteğe yönelik limitlerdir.

### <a name="timeout"></a>Zaman aşımı
| Ad | Limit |
| --- | --- |
| İstek Zaman Aşımı |120 Saniye |

### <a name="message-size"></a>İleti boyutu
| Ad | Limit | Notlar |
| --- | --- | --- |
| İleti boyutu |100 MB |API'lerden bazıları 100 MB'ın tamamını desteklenmez. |
| İfade değerlendirme limiti |131.072 karakter |`@concat()`, `@base64()`, `string` bu sınırı aşamaz. |

### <a name="retry-policy"></a>Yeniden deneme ilkesi
| Ad | Limit |
| --- | --- |
| Yeniden deneme sayısı |4 |

## <a name="run-duration-and-retention"></a>Çalışma süresi ve bekletme
Bunlar tek bir akış çalıştırmasına yönelik limitlerdir.

| Ad | Limit | Notlar |
| --- | --- | --- |
| Çalıştırma süresi |30 gün |Onaylar gibi bekleyen adımları olan iş akışlarını içerir. Bekleyen adımlar 30 gün sonra Zaman Aşımına uğrar. |
| Depolama bekletme |30 gün |Bu, çalıştırma başlangıç saatinden itibaren hesaplanır. |
| En az yinelenme aralığı |1 dakika | |
| En fazla yinelenme aralığı |500 gün | |

## <a name="looping-and-debatching-limits"></a>Döngü ve toplu iş ayırma limitleri
Bunlar tek bir akış çalıştırmasına yönelik limitlerdir.

| Ad | Limit | Notlar |
| --- | --- | --- |
| ForEach öğeleri |5,000 |Gerektiğinde daha büyük dizileri filtrelemek için filtreleme eylemini kullanabilirsiniz. |
| Yinelemelere kadar |5,000 | |
| SplitOn öğeleri |5,000 | |
| ForEach Paralelliği |1 | |

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
Microsoft SharePoint'i Microsoft Flow ve PowerApps ile nasıl kullanabileceğinize ilişkin [sınırlamalar](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) bulunur.

## <a name="ip-address-configuration"></a>IP adresi yapılandırması
Microsoft Flow isteklerinin hangi IP adresinden gönderileceği, akışı içeren [ortamın](environments-overview-admin.md) bulunduğu [bölgeye](regions-overview.md) bağlıdır. Şu anda akış senaryoları için kullanılabilir FQDN'ler yayımlanmamaktadır.

### <a name="logic-app-service"></a>Logic App Hizmeti
Bir akıştan yapılan çağrılar doğrudan Azure Logic Apps hizmetine gider. Bu çağrılara örnek olarak HTTP ya da HTTP + OpenAPI verilebilir. Bu çağrılar aşağıdaki IP adreslerinden gelir:

| Bölge | Giden IP |
| --- | --- |
| Asya |168.63.200.173, 13.75.89.159, 23.97.68.172, 13.75.94.173, 40.83.127.19, 52.175.33.254, 52.163.93.214, 52.187.65.81, 52.187.65.155, 13.76.133.155, 52.163.228.93, 52.163.230.166 |
| Avustralya |13.75.153.66, 104.210.89.222, 104.210.89.244, 13.75.149.4, 104.210.91.55, 104.210.90.241, 13.73.115.153, 40.115.78.70, 40.115.78.237, 13.73.114.207, 13.77.3.139, 13.70.159.205 |
| Kanada |52.233.29.92, 52.228.39.241, 52.228.39.244, 52.232.128.155, 52.229.120.45, 52.229.126.25 |
| Avrupa |13.79.173.49, 52.169.218.253, 52.169.220.174, 40.113.12.95, 52.178.165.215, 52.178.166.21, 13.95.155.53, 52.174.54.218, 52.174.49.6, 40.68.222.65, 40.68.209.23, 13.95.147.65 |
| Hindistan |52.172.157.194, 52.172.184.192, 52.172.191.194, 52.172.154.168, 52.172.186.159, 52.172.185.79, 52.172.9.47, 52.172.49.43, 52.172.51.140, 52.172.50.24, 52.172.55.231, 52.172.52.0 |
| Japonya |13.71.146.140, 13.78.84.187, 13.78.62.130, 13.71.158.3, 13.73.4.207, 13.71.158.120, 40.74.140.173, 40.74.81.13, 40.74.85.215, 40.74.140.4, 104.214.137.243, 138.91.26.45 |
| Amerika Birleşik Devletleri |137.135.106.54, 40.117.99.79, 40.117.100.228, 13.92.98.111, 40.121.91.41, 40.114.82.191, 52.160.90.237, 138.91.188.137, 13.91.252.184, 52.160.92.112, 40.118.244.241, 40.118.241.243 |

### <a name="services"></a>Hizmetler
Akış üzerinden bağlanan bir API'den (örneğin, SQP API veya SharePoint API) yapılan çağrılar aşağıda belirtilen IP adresinden gelir:

| Bölge | Giden IP |
| --- | --- |
| Asya |52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124 |
| Avustralya |13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35 |
| Kanada |52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56 |
| Avrupa |52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254 |
| Hindistan |52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245 |
| Japonya |104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229 |
| Amerika Birleşik Devletleri |104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Amerika Birleşik Devletleri (Erken Erişim) |52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29 |

Örneğin, Azure SQL veritabanınızın IP adreslerini güvenilir listeye eklemeniz gerekiyorsa bu adresleri kullanmanız gerekir.

Aşağıdaki tabloda, Microsoft Flow'un bağlandığı hizmetler listelenmiştir. Ağınızda bu hizmetlerden hiçbirinin engellenmediğinden emin olun.

Etki Alanları | Protokoller | Kullanımlar
--------|  ---------| -----
management.azure.com|https|Azure Resource Manager'a erişim.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Active Directory Kimlik Doğrulama Kitaplığı'na (ADAL) erişim.
graph.microsoft.com </br>graph.windows.net</br>|https|Profil fotoğrafı gibi kullanıcı bilgilerinin alınması için Azure AD Graph API'sine erişim.
*.azure-apim.net|https|Bağlayıcılar için Çalışma Zamanına erişim.
*.flow.microsoft.com|https|Microsoft Flow sitesine erişim.
*.powerapps.com|https|PowerApps sitesine erişim.
psux.azureedge.net|https|Microsoft Flow CDN erişimi.

