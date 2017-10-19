---
title: "Veri kaybı önleme (DLP) ilkelerine giriş. | Microsoft Docs"
description: "Microsoft Flow için veri kaybı önleme ilkelerine giriş."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/24/2016
ms.author: deonhe
ms.openlocfilehash: 29eaa9299e09c641538ab8f9dfbc9954bca66a3b
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="data-loss-prevention-dlp-policies"></a>Veri kaybı önleme (DLP) ilkeleri
## <a name="what-is-a-data-loss-prevention-policy"></a>Veri kaybı önleme ilkesi nedir?
Bir kuruluşun başarısı için verileri önemlidir. Veriler karar alma için kullanıma hazır olmalı, diğer yandan erişimi olmayan hedef kitlelerle paylaşılmaması için korunmalıdır. Bu verileri korumak için Microsoft Flow (Flow), paylaşılabilecek tüketici hizmetlerini/bağlayıcıya özgü iş verilerini tanımlayan ilkeler oluşturup uygulamanıza olanak sağlar. Verilerin nasıl paylaşılabileceğini tanımlayan bu ilkeler, veri kaybı önleme (DLP) ilkeleri olarak adlandırılır.

## <a name="why-create-a-dlp-policy"></a>Neden DLP ilkesi oluşturulmalıdır?
Paylaşılabilecek tüketici hizmetleri iş verilerini açıkça tanımlamak için DLP ilkesi oluşturun. Örneğin, Flow kullanan bir kuruluş, SharePoint’e depolanmış iş verilerinin Twitter akışında otomatik olarak yayımlanmasını istemeyebilir. Bunu önlemek için, SharePoint verilerinin tweet kaynağı olarak kullanılmasını engelleyen bir DLP ilkesi oluşturabilirsiniz.

## <a name="benefits-of-a-dlp-policy"></a>DLP ilkesinin yararları
* Verilerin kuruluş genelinde tek bir yolla yönetilmesini sağlar  
* Önemli iş verilerinin sosyal medya siteleri gibi hizmetlerde yanlışlıkla yayımlanmasını engeller.   

## <a name="managing-dlp-policies"></a>DLP ilkelerini yönetme
**Önkoşullar**  
DLP ilkeleri oluşturmak, düzenlemek veya silmek için aşağıdaki öğeler gereklidir: 

* Ortam yöneticisi veya kiracı yöneticisi izinleri. İzinler hakkında daha fazla bilgi için [ortamları konusuna](environments-overview-admin.md) bakın.  
* [Flow P2 lisansı](billing-questions.md).  

## <a name="create-a-dlp-policy"></a>DLP ilkesi oluşturma
**Önkoşullar**  
DLP ilkesi oluşturmak için en az bir ortamın izinlerine sahip olmanız gerekir.  

Şirketinizin SharePoint hesabına depolanmış verilerin Twitter’da yayınlanmasını engelleyen bir DLP ilkesi oluşturmak için aşağıdaki adımları izleyin:  

1. Veri İlkeleri sekmesinde **Yeni ilke** bağlantısını seçin:  
   ![Oturum açma](./media/prevent-data-loss/create-policy-1.png)    
2. Sayfanın üst kısmındaki **Veri İlkesi Adı** etiketinde DLP ilkesinin adını *Contoso için Güvenli Veri Erişimi* olarak girin:   
   ![Oturum açma](./media/prevent-data-loss/create-policy-2.png)  
3. **Şunun için geçerli** sekmesinde [ortam](environments-overview-admin.md) öğesini seçin.  
   **Not:** Ortam yöneticisi olarak yalnızca tek bir ortam için geçerli olan ilkeler oluşturabilirsiniz. Kiracı yöneticisi olarak tüm ortamlarda, bir veya daha fazla ortamda ya da belirli bir küme dışındaki tüm ortamlarda geçerli olan bir ilke oluşturabilirsiniz:  
   ![Oturum açma](./media/prevent-data-loss/create-policy-3.png)  
4. **Veri grupları** sekmesini seçin:  
   ![Oturum açma](./media/prevent-data-loss/create-policy-4.png)  
5. **Yalnızca iş verileri** grup kutusunun içindeki **+ Ekle** bağlantısını seçin:    
   ![Oturum açma](./media/prevent-data-loss/create-policy-5.png)  
6. **Hizmet ekle** sayfasından **SharePoint** ve **Salesforce** hizmetlerini seçin:  
   ![Oturum açma](./media/prevent-data-loss/create-policy-6.png)  
7. İş verileri paylaşmasına izin verilen hizmetleri eklemek için **Hizmet ekle** düğmesini seçin:    
   ![Oturum açma](./media/prevent-data-loss/create-policy-7.png)  
8. **İlkeyi Kaydet**’i seçin:  
   ![Oturum açma](./media/prevent-data-loss/create-policy-8.png)  
9. Birkaç dakika sonra yeni DLP ilkeniz veri kaybı önleme ilkeleri listesinde gösterilir:  
   ![Oturum açma](./media/prevent-data-loss/create-policy-9.png)  
10. **İsteğe bağlı** Yeni bir DLP ilkesinin mevcut olduğunu bildirmek için ekibinize e-posta gönderin veya başka bir iletişim yoluyla ulaşın.

Tebrikler, uygulamanın SharePoint ile Saleforce arasında veri paylaşmasını sağlayan ve diğer hizmetlerle veri paylaşımını engelleyen bir DLP ilkesi oluşturdunuz.  

**Not**: Bir hizmeti bir veri grubuna eklemek, hizmeti otomatik olarak diğer veri grubundan kaldırır. Örneğin, Twitter şu anda **yalnızca iş verileri** veri grubunda bulunuyorsa ve iş verilerinin Twitter ile paylaşılmasına izin vermek istemiyorsanız Twitter hizmetini **iş verilerine izin verilmez** adlı veri grubuna eklemeniz yeterlidir. Bu işlem Twitter’ı yalnızca iş verileri grubundan kaldırır.  

## <a name="data-sharing-violations"></a>Veri paylaşımı ihlalleri
Ana hatları yukarıda belirtilen DLP ilkesini oluşturduğunuzu varsayalım. Bir kullanıcı, Salesforce (veri grubu: **yalnızca iş verileri**) ile Twitter (veri grubu: **iş verileri kullanılamaz**) arasında veri paylaşımı yapan bir akış oluşturursa kullanıcıya, oluşturduğunuz veri kaybı önleme ilkesiyle çakışma olması nedeniyle akışın **askıya alındığı** bildirilir.  
![akış oluşturma](./media/prevent-data-loss/10.png)  

Kullanıcılarınız askıya alınan akışlarla ilgili olarak sizinle iletişime geçerse, şunları yapabilirsiniz:  

1. Bu örnekte, iş verilerini SharePoint ile Twitter arasında paylaşmak için işle ilgili geçerli bir sebep varsa, DLP ilkesini düzenleyebilirsiniz.  
2. Kullanıcıdan, akışı DLP ilkesine uyacak şekilde düzenlemesini isteyebilirsiniz.  
3. Kullanıcıdan, bu iki varlık arasında veri paylaşımı hakkında bir karar alınana kadar akışı askıya alınma durumunda bırakmasını isteyebilirsiniz.  

## <a name="find-a-dlp-policy"></a>DLP ilkesi bulma
### <a name="admins"></a>Yöneticiler
Yöneticiler belirli DLP ilkelerini bulmak için Yönetim merkezindeki arama özelliğini kullanabilir.  

**NOT** Yöneticiler, kuruluştaki kullanıcıların akış oluşturmadan önce ilkelerden haberdar olması için tüm DLP ilkelerini yayımlamalıdır.

### <a name="makers"></a>Oluşturucular
Yönetici izinlerine sahip değilseniz ve kuruluşunuzdaki DLP ilkeleri hakkında daha fazla bilgi edinmek istiyorsanız yöneticinize başvurun. Ayrıca [oluşturucu ortamları konusundan](environments-overview-maker.md) daha fazla bilgi edinebilirsiniz  

**NOT** DLP ilkeleri yalnızca yöneticiler tarafından düzenlenebilir veya silinebilir.  

## <a name="edit-a-dlp-policy"></a>DLP ilkesini düzenleme
1. https://admin.flow.microsoft.com adresine göz atarak Yönetim merkezini başlatın.  
2. Açılan Yönetim merkezinde sol taraftaki **Veri ilkeleri**’ni seçin.  
   ![Oturum açma](./media/prevent-data-loss/2.png)  
3. Var olan DLP ilkeleri listesinde arama yapın ve düzenlemek istediğiniz ilkenin yanındaki düzenle düğmesini seçin:  
   ![Oturum açma](./media/prevent-data-loss/3.png)  
4. Yapmak istediğiniz değişiklikleri yapın. Örneğin ortamı veya veri gruplarındaki hizmetleri değiştirebilirsiniz.  
5. Değişikliklerinizi kaydetmek için **İlkeyi Kaydet**’i seçin:  
   ![Oturum açma](./media/prevent-data-loss/create-policy-8.png)  

İlkeniz güncelleştirilmiştir. İlkenizi veri kaybı önleme ilkeleri listesinde bulup özelliklerini gözden geçirerek ilkenizde değişiklik yapıldığını onaylayabilirsiniz.   

**Not** Kiracı yöneticileri tarafından oluşturulan DLP ilkeleri, ortam yöneticileri tarafından görüntülenebilir, ancak düzenlenemez.  

## <a name="delete-a-dlp-policy"></a>DLP ilkesini silme
1. https://admin.flow.microsoft.com adresine göz atarak Yönetim merkezini başlatın.  
2. Açılan Yönetim merkezinde sol taraftaki **Veri ilkeleri**’ni seçin.  
   ![Oturum açma](./media/prevent-data-loss/2.png)  
3. Var olan DLP ilkeleri listesinde arama yapın ve silmek istediğiniz ilkenin yanındaki sil düğmesini seçin:  
   ![Oturum açma](./media/prevent-data-loss/3-delete.png)  
4. **Sil** düğmesini seçerek ilkeyi silmek istediğinizi onaylayın:  
   ![Oturum açma](./media/prevent-data-loss/4.png)  

İlkeniz silinmiştir. Sol taraftaki **Veri İlkeleri** bağlantısını seçip ilke listesini gözden geçirerek ilkenin veri kaybı önleme ilkeleri listesinde artık mevcut olmadığını onaylayabilirsiniz.   

## <a name="dlp-policy-permissions"></a>DLP ilkesi izinleri
DLP ilkeleri yalnızca kiracı ve ortam yöneticileri tarafından oluşturulup değiştirilebilir. [Ortamlar](environments-overview-admin.md) konusunda, izinler hakkında daha fazla bilgi edinebilirsiniz.  

## <a name="next-steps"></a>Sonraki adımlar
* [Ortamlar hakkında daha fazla bilgi edinin](environments-overview-admin.md)  
* [Microsoft Flow hakkında daha fazla bilgi edinin](getting-started.md)  
* [Yönetim merkezi hakkında daha fazla bilgi edinin](introduction-to-the-admin-center.md)  

