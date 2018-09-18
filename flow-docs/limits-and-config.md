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
ms.date: 06/19/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1d4585d18b83975ba888a7685e8556c778889ee1
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690595"
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

## <a name="looping-and-debatching-limits"></a>Döngü ve toplu iş ayırma limitleri
Bunlar tek bir akış çalıştırmasına yönelik limitlerdir.

| Ad | Limit | Notlar |
| --- | --- | --- |
| Her bir öğeye uygulayın |100.000 |100.000 yalnızca premium planlarda kullanılabilir. Aksi takdirde, 5.000 ile sınırlı kalırsınız. Gerektiğinde daha büyük dizileri filtrelemek için filtreleme eylemini kullanabilirsiniz. |
| Yinelemelere kadar |5,000 | |
| SplitOn öğeleri |100.000 |Her birine uygula seçeneğinde olduğu gibi, premium planda değilseniz sınır 5.000’dir. |
| Her birine uygula Paralellik |50 |Varsayılan olarak döngüler birbiri ardına çalışır (aslına bakılırsa parallellik 1). Varsayılan olarak 50’ye kadar paralel akış yapılandırabilirsiniz. |
| Eylem yürütme işlemleri 5 dakikada bir yapılır | 100.000 | Ayrıca, bir iş yükünü gerektiğinde birden fazla akış oluşturmak üzere dağıtabilirsiniz. |
| Eylemler eş zamanlı giden çağrılar | Yaklaşık 2.500 | Eş zamanlı istek sayısını veya süreyi gerektiği gibi azaltın. | 

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

> [!IMPORTANT]
>   Var olan yapılandırmalarınızı en geç 1 Eylül 2018 tarihine kadar güncelleştirerek akışlarınızın bulunduğu bölgeler için aşağıdaki listede yer alan IP adreslerini kullanmalarını sağlayın.

Akış üzerinden bağlanan bir API’den (örneğin, SQP API veya SharePoint API) yapılan çağrılar aşağıda belirtilen IP adresinden gelir:

| Bölge | Giden IP |
| --- | --- |
| Asya |13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19, 52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 52.187.53.78, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124, 23.97.72.250 |
| Avustralya |13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174, 13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.188.38, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35, 13.70.88.23 |
| Brezilya |191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Kanada |13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152, 52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56, 52.229.123.161, 52.233.27.68 |
| Avrupa |13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 52.178.37.42, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254, 52.164.249.26, 137.117.161.181 |
| Hindistan |104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218, 52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.49.180, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245, 52.172.153.107 |
| Japonya |13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248, 104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 104.214.151.229, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229, 13.78.121.151 |
| Birleşik Krallık |51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Amerika Birleşik Devletleri |13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49, 104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 40.78.144.221, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 13.93.159.171, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191, 23.96.11.216 |
| Amerika Birleşik Devletleri (Erken Erişim) |13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157, 52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 52.161.31.35, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29, 13.66.208.24 |

Örneğin, Azure SQL veritabanınızın IP adreslerini yetkilendirmeniz gerekiyorsa bu adresleri kullanmanız gerekir.

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
nps.onyx.azure.net|https|NPS’ye (Net Promoter Score) erişim.

