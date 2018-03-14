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
ms.date: 02/28/2018
ms.author: deonhe
ms.openlocfilehash: 7dbf6296383551d82d22682121210f1cd339b65e
ms.sourcegitcommit: 22a883c30c859b6193fc2a619e753d71247f5e15
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2018
---
# <a name="data-loss-prevention-dlp-policies"></a>Veri kaybı önleme (DLP) ilkeleri

Bu belgede size veri kaybı önleme ilkeleri sunulur. Bu ilkeler, kuruluş verilerinizin tanımladığınız bağlayıcıların bir listesiyle paylaşılmasını önleme konusunda size yardımcı olur.

## <a name="whats-a-data-loss-prevention-policy"></a>Veri kaybı önleme ilkesi nedir?

Bir kuruluşun başarısı için verileri önemlidir. Kuruluşun verilerinin karar alma süreci için kullanıma hazır olması gerekir ve erişim sahibi olmaması gereken kitlelerle paylaşımın önlenmesi amacıyla bu veriler koruma altına alınmalıdır. Bu verilerin korunması için Microsoft Flow, hangi tüketici bağlayıcılarının iş verilerine erişebileceğini ve bunları paylaşabileceğini tanımlayan ilkeler oluşturup uygulamanıza olanak sağlar. Verilerin nasıl paylaşılabileceğini tanımlayan bu ilkeler, veri kaybı önleme (DLP) ilkeleri olarak adlandırılır.

## <a name="why-create-a-dlp-policy"></a>Neden DLP ilkesi oluşturulmalıdır?

Hangi tüketici bağlayıcılarının iş verilerinize erişebileceğini ve bunları paylaşabileceğini açıkça tanımlamak için DLP ilkesi oluşturursunuz. Örneğin, Microsoft Flow kullanan bir kuruluş, SharePoint’teki iş verilerinin Twitter akışında otomatik olarak yayımlanmasını istemeyebilir. Bunu önlemek için, SharePoint verilerinin tweet kaynağı olarak kullanılmasını engelleyen bir DLP ilkesi oluşturursunuz.

## <a name="benefits-of-a-dlp-policy"></a>DLP ilkesinin yararları

* Verilerin kuruluş genelinde tek bir yolla yönetilmesini sağlar.
* Önemli iş verilerinin sosyal medya siteleri gibi bağlayıcılarda yanlışlıkla yayımlanmasını engeller.

## <a name="managing-dlp-policies"></a>DLP ilkelerini yönetme

### <a name="prerequisites-for-managing-dlp-policies"></a>DLP ilkelerini yönetmeye ilişkin önkoşullar

* Ortam yöneticisi veya kiracı yöneticisi izinleri.

    [Ortamlar makalesinde](environments-overview-admin.md) izinler hakkında daha fazla bilgi edinebilirsiniz.
* Bir [Microsoft Flow P2 lisansı](billing-questions.md).

## <a name="create-a-dlp-policy"></a>DLP ilkesi oluşturma

### <a name="prerequisites-for-creating-dlp-policies"></a>DLP ilkesi oluşturmaya ilişkin önkoşullar

DLP ilkesi oluşturmak için en az bir ortamın izinlerine sahip olmanız gerekir.

Şirketinizin SharePoint sitesindeki verilerin Twitter’da yayınlanmasını engelleyen bir DLP ilkesi oluşturmak için şu adımları uygulayın:

1. [Microsoft Flow Yönetim Merkezi](https://admin.flow.microsoft.com)’nde (Yönetim merkezi) oturum açın.

1. Veri İlkeleri sekmesini ve sonra **Yeni ilke** bağlantısını seçin:

    ![Oturum açma](./media/prevent-data-loss/create-policy-1.png)
1. **Veri grupları** sekmesini seçin.

1. Sayfanın üst kısmındaki **Veri İlkesi Adı** etiketinde DLP ilkesinin adını *Contoso için Güvenli Veri Erişimi* olarak girin:

    ![Oturum açma](./media/prevent-data-loss/create-policy-2.png)

1. **Ortamlar** sekmesinde [ortam](environments-overview-admin.md) seçeneğini belirleyin.

    > [!NOTE]
    > Ortam yöneticisi olarak yalnızca tek bir ortam için geçerli olan ilkeler oluşturabilirsiniz. Kiracı yöneticisi olarak, ortamların herhangi bir bileşimi için geçerli olan ilkeler oluşturabilirsiniz.
    >
    >

    ![Ortam seçme](./media/prevent-data-loss/create-policy-3.png)

1. **Veri grupları** sekmesini seçin:

    ![veri grupları sekmesini seçme](./media/prevent-data-loss/create-policy-4.png)

1. **Yalnızca iş verileri** grup kutusunun içinde bulunan **Ekle** bağlantısını seçin:

    ![ekle bağlantısını seçme](./media/prevent-data-loss/create-policy-5.png)

1. **Bağlayıcı ekle** sayfasından **SharePoint** ve **Salesforce** bağlayıcılarını seçin:

   ![bağlayıcıları seçme](./media/prevent-data-loss/create-policy-6.png)

1. İş verilerini paylaşabilen bağlayıcıları eklemek için **Bağlayıcı ekle** seçeneğini belirleyin.

1. Ekranın sağ üst köşesinde **İlkeyi Kaydet** seçeneğini belirleyin.

1. Birkaç dakika sonra yeni DLP ilkeniz veri kaybı önleme ilkeleri listesinde gösterilir:

    ![DLP listesi](./media/prevent-data-loss/create-policy-9.png)

1. **İsteğe bağlı** Yeni bir DLP ilkesinin mevcut olduğunu bildirmek için ekibinize e-posta gönderin veya başka bir iletişim yoluyla ulaşın.

Tebrikler, uygulamanın SharePoint ile Salesforce arasında veri paylaşmasını sağlayan ve diğer hizmetlerle veri paylaşımını engelleyen bir DLP ilkesi oluşturdunuz.

> [!NOTE]
> Bir hizmeti bir veri grubuna eklemek, hizmeti otomatik olarak diğer veri grubundan kaldırır. Örneğin, Twitter şu anda **yalnızca iş verileri** veri grubunda bulunuyorsa ve iş verilerinin Twitter ile paylaşılmasına izin vermek istemiyorsanız Twitter hizmetini **iş verilerine izin verilmez** adlı veri grubuna eklemeniz yeterlidir. Bu işlem Twitter’ı yalnızca iş verileri grubundan kaldırır.
>
>

## <a name="data-sharing-violations"></a>Veri paylaşımı ihlalleri

Ana hatları yukarıda belirtilen DLP ilkesini oluşturduğunuzu varsayalım. Bir kullanıcı, Salesforce (veri grubu: **yalnızca iş verileri**) ile Twitter (veri grubu: **iş verileri kullanılamaz**) arasında veri paylaşımı yapan bir akış oluşturursa kullanıcıya, oluşturduğunuz veri kaybı önleme ilkesiyle çakışma olması nedeniyle akışın **askıya alındığı** bildirilir.

![akış oluşturma](./media/prevent-data-loss/10.png)

Kullanıcılarınız askıya alınan akışlarla ilgili olarak sizinle iletişime geçerse, şunları yapabilirsiniz:

1. Bu örnekte, iş verilerini SharePoint ile Twitter arasında paylaşmak için işle ilgili geçerli bir neden varsa, DLP ilkesini düzenleyebilirsiniz.

1. Kullanıcıdan, akışı DLP ilkesine uyacak şekilde düzenlemesini isteyebilirsiniz.

1. Kullanıcıdan, bu iki varlık arasında veri paylaşımı hakkında bir karar alınana kadar akışı askıya alınma durumunda bırakmasını isteyebilirsiniz.

## <a name="find-a-dlp-policy"></a>DLP ilkesi bulma

### <a name="admins"></a>Yöneticiler

Yöneticiler belirli DLP ilkelerini bulmak için Yönetim merkezindeki arama özelliğini kullanabilir.

> [!NOTE]
> Yöneticiler, kuruluştaki kullanıcıların akış oluşturmadan önce ilkelerden haberdar olması için tüm DLP ilkelerini yayımlamalıdır.
>
>

### <a name="makers"></a>Oluşturucular

Yönetici izinlerine sahip değilseniz ve kuruluşunuzdaki DLP ilkeleri hakkında daha fazla bilgi edinmek istiyorsanız yöneticinize başvurun. Ayrıca [oluşturucu ortamları makalesinde](environments-overview-maker.md) daha fazla bilgi edinebilirsiniz

> [!NOTE]
> DLP ilkeleri yalnızca yöneticiler tarafından düzenlenebilir veya silinebilir.
>
>

## <a name="edit-a-dlp-policy"></a>DLP ilkesini düzenleme

1. [Yönetim merkezini](https://admin.flow.microsoft.com) başlatın.

1. Açılan Yönetim merkezinde sol taraftaki **Veri ilkeleri**’ni seçin.

    ![veri ilkelerini seçme](./media/prevent-data-loss/2.png)

1. Mevcut DLP ilkeleri listesinde arama yapın ve düzenlemek istediğiniz ilkenin yanındaki düzenle düğmesini seçin.

1. İlkede gerekli değişiklikleri yapın. Örneğin ortamı veya veri gruplarındaki hizmetleri değiştirebilirsiniz.

1. Değişikliklerinizi kaydetmek için **İlkeyi Kaydet**’i seçin.

> [!NOTE]
> Kiracı yöneticileri tarafından oluşturulan DLP ilkeleri, ortam yöneticileri tarafından görüntülenebilir, ancak düzenlenemez.
>
>

## <a name="delete-a-dlp-policy"></a>DLP ilkesini silme

1. [Yönetim merkezini](https://admin.flow.microsoft.com) başlatın.

1. Sol taraftaki **Veri ilkeleri** sekmesini seçin.

    ![veri ilkeleri sekmesini seçme](./media/prevent-data-loss/2.png)

1. Mevcut DLP ilkeleri listesinde arama yapın ve sonra silmek istediğiniz ilkenin yanındaki sil düğmesini seçin:

    ![sil düğmesini seçme](./media/prevent-data-loss/3-delete.png)

1. **Sil** düğmesini seçerek ilkeyi silmek istediğinizi onaylayın:

    ![ilkeyi silmek istediğinizi onaylama](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>DLP ilkesi izinleri

DLP ilkeleri yalnızca kiracı ve ortam yöneticileri tarafından oluşturulup değiştirilebilir. [Ortamlar](environments-overview-admin.md) makalesinde izinler hakkında daha fazla bilgi edinebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

* [Ortamlar hakkında daha fazla bilgi edinin](environments-overview-admin.md)
* [Microsoft Flow hakkında daha fazla bilgi edinin](getting-started.md)
* [Yönetim merkezi hakkında daha fazla bilgi edinin](admin-center-introduction.md)
* [Veri tümleştirmesi hakkında daha fazla bilgi edinin](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
