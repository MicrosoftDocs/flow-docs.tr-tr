---
title: "API Bağlayıcısı olarak sertifika için gönderme | Microsoft Docs"
description: "Bağlayıcıya sertifika verildiğinde, Microsoft Flow, PowerApps ve Logic Apps’in tüm kullanıcıları tarafından kullanılabilir duruma gelir."
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 7eb357458161ba398864604bfe8912636ddc4d39
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="submit-your-connectors-for-microsoft-certification"></a>Bağlayıcılarınızı Microsoft sertifikası için gönderme
Özel bağlayıcıları Microsoft Flow, Azure Logic Apps ve Microsoft PowerApps’te tüm kullanıcılar için genel olarak kullanılabilir hale getirmek istiyorsanız, bağlayıcınızı gözden geçirme, doğrulama ve yayın onayı için Microsoft’a gönderin. 

## <a name="certification-criteria"></a>Sertifika ölçütleri
| Özellik | Ayrıntılar | Gerekli veya Önerilir |
| --- | --- | --- |
| Hizmet Olarak Yazılım (SaaS) uygulaması |Logic Apps, Flow ve PowerApps için uygun bir kullanıcı senaryosunu karşılar. |Gerekli |
| Kimlik Doğrulama Türü |API’niz OAuth2, API Anahtarı veya Temel Kimlik Doğrulamasını desteklemelidir. |Gerekli |
| Destek |Müşterilerin yardım alabileceği bir destek görevlisi sağlamalısınız. |Gerekli |
| Kullanılabilirlik ve çalışma süresi |Uygulamanız en az %99,9 çalışma süresine sahip olmalıdır. |Önerilir |
|  | | |

Ayrıca, bir Microsoft iş ortağı veya Bağımsız Yazılım Satıcısı (ISV) değilseniz ve bir bağlayıcıyı doğrulayıp genel olarak yayınlamak istiyorsanız, temel alınan hizmetin sahibi olmanız veya API’yi kullanmak için açık hakları sunmanız gerekir.

Sertifika verilmeden önce bağlayıcınız iki aşamada gözden geçirilir: 

1. İşlevsellik Doğrulaması
   
    Özel bağlayıcının şu özellikleri değerlendirilir:
   
   * Özel bağlayıcı sihirbazının Tanım bölümünde geçersiz swagger veya JSON hataları
   * Sihirbazın Test bölümünde çalışma zamanı ve şema doğrulama hataları
     
     Sonuç olarak, her işlem istemci tarafı hatalarına karşı Flow, Logic Apps ve PowerApps’te baştan sona test edilir.
2. İçerik Doğrulaması
   
    İyi yazılmış bir bağlayıcı, her varlık için kolay adlar ve açıklamalar kullanır. Her işlem, girdi parametresi ve yanıt özniteliğinin şunları içerdiğinden emin olmak için swagger’ınızı değerlendiririz:
   
   * [Özet](../logic-apps/custom-connector-openapi-extensions.md#summary)
   * [Açıklama](../logic-apps/custom-connector-openapi-extensions.md#description)
   * [Görünürlük bilgileri](../logic-apps/custom-connector-openapi-extensions.md#visibility)

## <a name="nominate-and-submit-your-connector-to-microsoft-for-certification"></a>Bağlayıcınızı sertifika için aday gösterin ve Microsoft’a gönderin
Sertifika için başvurmak için şu adımları izleyin:

1. **Aday göster**
   
   1. [Adaylığınızı gönderin](https://go.microsoft.com/fwlink/?linkid=848754).
   2. Aldığınız iki taraflı Gizlilik Sözleşmesi ve İş Ortağı Sözleşmesini imzalayın. 
      Microsoft, devam etmeden önce bu sözleşmelerin imzalanmasını gerekli kılar. 
      Daha sonra bağlayıcınızın sertifika ölçütlerini karşılayıp karşılamadığını denetleyebiliriz. 
   3. Bağlayıcınız onaylanırsa, Microsoft sizi katılma yönergeleri konusunda bilgilendirir.
2. **Gözden geçirme**
   
   1. Aşağıdaki bilgileri gözden geçirilmesi için adaylık yetkilinize gönderin:
      
      * API’nizi tanımlayan OpenAPI dosyası
      * Bağlayıcınızı temsil eden simge dosyası (.png veya .jpg). (Simgeniz 230 piksel kare içinde ~160 piksel bir logo içermelidir. Renkli bir arka plan üzerinde beyaz bir logo tercih edilir.)
      * Onaltılık biçimde simgenizin marka rengi, bu renk simge dosyasındaki renkli arka planla eşleşmelidir
      * Doğrulama için bir test hesabı
      * Destek yetkilisi
   2. Daha fazla bilgiye ihtiyacımız olursa, sizinle iletişime geçeriz.
3. **Yayımlama**
   
    Bağlayıcınızın işlevselliğini ve içeriğini doğruladıktan sonra, bağlayıcıyı tüm ürünler ve bölgeler genelinde dağıtıma hazırlarız. Genellikle, sertifika ve dağıtım işlemi 3 haftaya kadar sürer.
   
    Varsayılan olarak, tüm bağlayıcılar "premium" kategorisinde yayımlanır. 
    Uygulamanız Azure üzerinde oluşturulduysa, bağlayıcınızın “standart” bağlayıcı olarak listelenmesi ve böylece Office 365 Kurumsal planları kapsamındaki tüm kullanıcılara sunulabilmesi için başvurabilirsiniz. 
    Daha fazla bilgi için, adaylık konusunda ilgili kişiye başvurun.

