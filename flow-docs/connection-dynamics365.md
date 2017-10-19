---
title: "Dynamics 365 ile bir akış oluşturma (çevrimiçi) | Microsoft Docs"
description: "Bir Dynamics 365 bağlantısı ve Microsoft Flow kullanarak faydalı iş akışları oluşturma"
services: 
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
ms.openlocfilehash: 5ef3de417b1557644ce9bfcd935353e017ceb676
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Dynamics 365 kullanarak akış oluşturma (çevrimiçi)
Bir Dynamics 365 bağlayıcısı kullanarak, Dynamics 365 veya başka bir hizmette bir olay gerçekleştiğinde başlatılan ve Dynamics 365 veya başka bir hizmette eylem gerçekleştiren akışlar oluşturabilirsiniz. 

Microsoft Flow’da dosyaları eşitlemek, bildirimler almak, veri toplamak ve daha fazlası için, sık kullandığınız uygulamalar ve hizmetler arasında otomatik iş akışları oluşturabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Flow kullanmaya başlama](getting-started.md).

## <a name="create-a-flow-from-a-template"></a>Şablondan akış oluşturma
Aşağıdaki örneklere benzer çok sayıda şablondan birini kullanarak akış oluşturabilirsiniz:

* Dynamics 365’te bir nesne oluşturulduğunda, SharePoint’te bir liste öğesi oluşturun.
* Bir Excel tablosundan Dynamics 365 müşteri adayı kayıtları oluşturun.
* Dynamics 365 hesaplarını Dynamics 365 for Operations’taki müşterilere kopyalayın.

Bir şablondan akış oluşturmak için, bu adımları izleyin.

1. [Microsoft Flow web sitesinde](https://flow.microsoft.com/) oturum açın.
2. **Hizmetler**’e ve sonra **Dynamics 365**’e tıklayın veya dokunun.
3. Çeşitli şablonlar kullanılabilir. Başlamak için, istediğiniz şablonu seçin.

## <a name="create-a-task-from-a-lead"></a>Bir müşteri adayından görev oluşturma
İhtiyacınız olan akış için bir şablon yoksa, sıfırdan bir akış oluşturun. Bu kılavuzda, Dynamics 365’te bir müşteri adayı oluşturulduğunda Dynamics 365’te bir görevin nasıl oluşturulacağı gösterilmektedir.

1. [Microsoft Flow web sitesinde](https://flow.microsoft.com/) oturum açın.
2. **Akışlarım**’a tıklayın veya dokunun ve sonra **Boş akış oluştur**’a tıklayın veya dokunun.
3. Akış tetikleyicileri listesinde, **Dynamics 365 - Bir kayıt oluşturulduğunda** seçeneğine tıklayın veya dokunun.
4. İstenirse Dynamics 365’te oturum açın.
5. **Kuruluş Adı** altında, akışın dinlemesini istediğiniz Dynamics 365 örneğini seçin.
6. **Varlık Adı** altında, dinlemek istediğiniz varlığı seçin. Bu varlık, akışı başlatan tetikleyici olarak davranır.
   
     Bu kılavuz için, **Müşteri Adayları**’nı seçin.
   
    ![Akış ayrıntıları](./media/connection-dynamics365/flow-details.png)
7. **Yeni adım**'a ve ardından **Eylem ekle**'ye tıklayın veya dokunun.
8. **Dynamics 365 – Yeni kayıt oluştur**’a tıklayın veya dokunun.
9. **Kuruluş Adı** altında, akışın kaydı oluşturmasını istediğiniz Dynamics 365 örneğini seçin. Olayın tetiklendiği örnek ile aynı örnek olmasının gerekmediğine dikkat edin.
10. **Varlık Adı** altında, olay gerçekleştiğinde bir kayıt oluşturacak olan varlığı seçin.
    
     Bu kılavuz için, **Görevler**’i seçin.
11. Bir **Konu** kutusu görüntülenir. Tıkladığınızda veya dokunduğunuzda, bu alanlardan birini seçebileceğiniz bir dinamik içerik bölmesi görüntülenir.
    
    * **Soyadı**. Bu alanı seçerseniz, görev oluşturulduğunda müşteri adayının soyadı görevin **Konu** alanına eklenir.
    * **Konu başlığı**. Bu alanı seçerseniz, görev oluşturulduğunda müşteri adayı için **Konu başlığı** alanı görevin **Konu** alanına eklenir.
    
    Bu kılavuz için, **Konu başlığı**’nı seçin.
    
    ![Akış konu başlığı ekleme](./media/connection-dynamics365/flow-addtopic.png)
    
    > **İpucu:** Dinamik içerik bölmesinde, varlıkla ilişkili daha fazla alan görüntülemek için **Daha fazla**’ya tıklayın veya dokunun. Örneğin, görevin **Konu** alanını müşteri adayının **Şirket Adı**, **Müşteri**, **Açıklama** veya **E-posta** alanı ile doldurabilirsiniz.
    > 
    > 
12. **Akış oluştur**'a tıklayın veya dokunun.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Bİr Dynamics 365 görevinden Wunderlist görevi oluşturma
Bu kılavuzda, Dynamics 365’te bir görev oluşturulduğunda [Wunderlist](http://www.wunderlist.com)’te bir görevin nasıl oluşturulacağı gösterilmektedir. Wunderlist yapılacaklar listeleri oluşturmak, anımsatıcılar eklemek veya günlük işleri izlemek için kullanabileceğiniz İnternet tabanlı bir hizmettir.

1. [Microsoft Flow web sitesinde](https://flow.microsoft.com/) oturum açın.
2. **Akışlarım**’a tıklayın veya dokunun ve sonra **Boş akış oluştur**’a tıklayın veya dokunun.
3. Akış tetikleyicileri listesinde, **Dynamics 365 - Bir kayıt oluşturulduğunda** seçeneğine tıklayın veya dokunun.
4. **Kuruluş Adı** altında, akışın dinlemesini istediğiniz Dynamics 365 örneğini seçin.
5. **Varlık Adı** altında, dinlemek istediğiniz varlığı seçin. Bu varlık, akışı başlatmak için tetikleyici olarak davranır.
   
    Bu kılavuz için, **Görevler**’i seçin.
6. **Yeni adım**'a ve ardından **Eylem ekle**'ye tıklayın veya dokunun.
7. *Görev oluştur* yazın ve sonra **Wunderlist – Görev oluştur**’a tıklayın veya dokunun.
8. **Liste kimliği** altında, **gelen kutusu** seçeneğini belirleyin.
9. **Başlık** altında, dinamik içerik bölmesinden **Konu**’yu seçin.
10. **Akış oluştur**'a tıklayın veya dokunun.  

## <a name="specify-advanced-options"></a>Gelişmiş seçenekleri belirtme
Bir akışa adım eklediğinizde, verilerin akışta nasıl filtreleneceğini denetleyen bir filtre veya sıralama sorgusu eklemek için **Gelişmiş seçenekleri göster**’e tıklayabilir veya dokunabilirsiniz.

Örneğin, yalnızca etkin kişileri almak için bir filtre sorgusu kullanabilir ve bu kişileri soyadına göre sıralayabilirsiniz. Bunu yapmak için, **statuscode eq 1** OData filtre sorgusunu girin ve dinamik içerik bölmesinden **Soyadı**’nı seçin. Filtre ve sıralama ölçütü sorguları hakkında daha fazla bilgi için, bkz. [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) ve [MSDN: $orderby](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Akış sıralama ölçütü sorgusu](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Gelişmiş seçenekleri kullanırken en iyi yöntemler
Bir alana değer eklediğinizde, bir değer yazarken veya dinamik içerik bölmesinden değer seçerken alan türüne uymanız gerekir.

| Alan türü | Nasıl kullanılır? | Nerede bulunur? | Ad | Veri türü |
| --- | --- | --- | --- | --- |
| Metin alanları |Metin alanı tek satırlık bir metin veya bir metin tür alanı olan dinamik içerik gerektirir. Örnekler arasında **Kategori** ve **Alt Kategori** alanları bulunur. |**Ayarlar** > **Özelleştirmeler** > **Sistemi Özelleştir** > **Varlıklar** > **Görev** > **Alanlar** |**kategori** |**Tek Satırlık Metin** |
| Tamsayı alanları |Bazı alanlar tamsayı veya bir tamsayı tür alanı olan dinamik içerik gerektirir. Örnekler arasında **Tamamlanma Yüzdesi** ve **Süre** bulunur. |**Ayarlar** > **Özelleştirmeler** > **Sistemi Özelleştir** > **Varlıklar** > **Görev** > **Alanlar** |**tamamlanma yüzdesi** |**Tamsayı** |
| Tarih alanları |Bazı alanlar aa/gg/yyyy biçiminde girilen bir tarih veya bir tarih tür alanı olan dinamik içerik gerektirir. Örnekler arasında **Oluşturulma Tarihi**, **Başlangıç Tarihi**, **Gerçek Başlangıç**, **Son Bekletme Zamanı**, **Gerçek Bitiş** ve **Son Tarih** bulunur. |**Ayarlar** > **Özelleştirmeler** > **Sistemi Özelleştir** > **Varlıklar** > **Görev** > **Alanlar** |**oluşturulma tarihi** |**Tarih ve Saat** |
| Kayıt kimliği ve arama türü gerektiren alanlar |Başka bir varlık kaydına başvuran bazı alanlar kayıt kimliğini ve arama türünü gerektirir. |**Ayarlar** > **Özelleştirmeler** > **Sistemi Özelleştir** > **Varlıklar** > **Hesap** > **Alanlar** |**hesap kimliği** |**Birincil Anahtar** |

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Kayıt kimliği ve arama türü gerektiren alanlara daha fazla örnek
Önceki tabloya ek olarak, aşağıda dinamik içerik listesinden seçilen değerler ile çalışmayan alanlara daha fazla örnek verilmiştir. Bunun yerine, bu alanlar PowerApps alanlarına kayıt kimliğinin ve arama türünün girilmesini gerektirir.

* **Sahip** ve **Sahip Türü**.
  
  * **Sahip** alanı geçerli bir kullanıcı veya takım kaydı kimliği olmalıdır.
  * **Sahip Türü**, **sistem kullanıcıları** veya **takımlar** olmalıdır.
* **Müşteri** ve **Müşteri Türü**.
  
  * **Müşteri** alanı geçerli bir hesap veya ilgili kişi kaydı kimliği olmalıdır.
  * **Müşteri Türü**, **hesaplar** veya **ilgili kişiler** olmalıdır.
* **İlgili** ve **İlgili Türü**.
  
  * **İlgili** alanı bir hesap veya ilgili kişi kaydı kimliği gibi geçerli bir kayıt kimliği olmalıdır.
  * **İlgili Türü** kayıt için arama türü olmalıdır (örneğin, **hesaplar** veya **ilgili kişiler**).

Bu örnek, kayıt kimliğine karşılık gelen bir hesap kaydı ekleyerek bunu görevin **İlgili** alanına ekler.

  ![Akış kayıt kimliği ve tür hesabı](./media/connection-dynamics365/flow-recordid-account.png)

Bu örnek ayrıca görevi kullanıcının kayıt kimliğine dayalı olarak belirli bir kullanıcıya atar.

  ![Akış kayıt kimliği ve tür kullanıcısı](./media/connection-dynamics365/flow-recordid-user.png)

Bir kaydın kimliğini bulmak için, bu konudaki [Kayıt kimliğini bulma](#find-the-record-id) bölümüne bakın.

> **Önemli:** Alanlar "Yalnızca dahili kullanım içindir" açıklamasına sahipse bir değer içermemelidir. Bu alanlar **Geçiş yapılan yol**, **Ek Parametreler** ve **Saat Dilimi Kuralı Sürüm Numarası**’nı içerir.
> 
> 

## <a name="find-the-records-id"></a>Kaydın kimliğini bulma
1. Dynamics 365 web uygulamasında, hesap kaydı gibi bir kayıt açın.
2. Eylemler araç çubuğunda, **Öne Çıkar**
   ![kaydı öne çıkar](./media/connection-dynamics365/popout.png)’a tıklayın veya dokunun (veya tam URL’yi varsayılan e-posta programınıza kopyalamak için **E-POSTA İLE BAĞLANTI GÖNDER**’e tıklayın veya dokunun).
   
    Web tarayıcısının adres çubuğundaki URL, %7b ile %7d kodlama karakterleri arasında kayıt kimliğini içerir.
   
   ![Kayıt kimliği](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>İlgili konular
[Bir akışla ilgili sorunları giderme](fix-flow-failures.md)

[Kuruluşunuzda Flow ile ilgili soru-cevap](organization-q-and-a.md)

[Sık sorulan sorular](frequently-asked-questions.md)

