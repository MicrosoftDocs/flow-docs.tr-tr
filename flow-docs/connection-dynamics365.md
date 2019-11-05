---
title: Dynamics 365 ile akış oluşturma (çevrimiçi) | Microsoft Docs
description: Dynamics 365 bağlantısı kullanarak faydalı iş akışları oluşturun ve Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a138cef3761b188998766a60ceb84619ae5f0a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546909"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Dynamics 365 kullanarak akış oluşturma (çevrimiçi)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Dynamics 365 bağlayıcısını kullanarak Dynamics 365 ' de bir olay gerçekleştiğinde veya başka bir hizmette, daha sonra Dynamics 365 veya başka bir hizmette eylem gerçekleştiren akışlar oluşturabilirsiniz. 

Microsoft Flow, dosyaları eşitlemeniz, bildirimler almak, veri toplamak ve daha fazlası için sık kullandığınız uygulamalar ve hizmetler arasında otomatik iş akışları oluşturabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Flow kullanmaya başlama](getting-started.md).

> [!IMPORTANT] 
> Bir akış tetikleyicisi çağırmak için akışta kullanılan Common Data Service varlığının **değişiklik izleme** etkinleştirilmiş olması gerekir. Daha fazla bilgi: [veri eşitlemeyi denetlemek için değişiklik Izlemeyi etkinleştirme](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Şablondan akış oluşturma
Aşağıdaki örnekler gibi birçok şablondan birini kullanarak akış oluşturabilirsiniz:

* Dynamics 365 ' de bir nesne oluşturulduğunda, SharePoint 'te bir liste öğesi oluşturun.
* Bir Excel tablosundan Dynamics 365 müşteri adayı kayıtları oluşturun.
* Dynamics 365 hesaplarını, Işlemler için Dynamics 365 ' de müşterilere kopyalayın.

Bir şablondan akış oluşturmak için aşağıdaki adımları izleyin.

1. [Microsoft Flow web sitesinde](https://flow.microsoft.com/)oturum açın.
2. **Hizmetler**' e tıklayın veya dokunun ve ardından **Dynamics 365**' e tıklayın veya dokunun.
3. Çeşitli şablonlar var. Başlamak için istediğiniz şablonu seçin.

## <a name="create-a-task-from-a-lead"></a>Bir müşteri adayının görevi oluşturma
İhtiyacınız olan bir şablon yoksa sıfırdan bir akış oluşturun. Bu izlenecek yol, Dynamics 365 ' de bir müşteri adayı oluşturulduğunda Dynamics 365 ' de bir görevin nasıl oluşturulacağını gösterir.

1. [Microsoft Flow web sitesinde](https://flow.microsoft.com/)oturum açın.
2. **Akışlarım**' a tıklayın veya dokunun ve ardından **boş oluştur**' a tıklayın veya dokunun.
3. Akış Tetikleyicileri listesinde, **bir kayıt oluşturulduğunda Dynamics 365-** ' ya tıklayın veya dokunun.
4. İstenirse Dynamics 365 ' de oturum açın.
5. **Kuruluş adı**altında, akışın dinlemesini istediğiniz Dynamics 365 örneğini seçin.
6. **Varlık adı**altında, dinlemek istediğiniz varlığı seçin. Bu işlem, akışı Başlatan bir tetikleyici olarak davranır.
   
     Bu izlenecek yol için **müşteri adayları**' nı seçin.
   
    ![Akış ayrıntıları](./media/connection-dynamics365/flow-details.png)
    > ÖNEMLI Flow 'un Dynamics 365 varlığında tetiklenmesi için varlık tanımında **değişiklik izleme** etkinleştirilmiş olması gerekir. Bkz. [veri eşitlemeyi denetlemek için değişiklik Izlemeyi etkinleştirme](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. **Yeni adım**' a ve ardından **Eylem Ekle**' ye tıklayın veya dokunun.
8. **Dynamics 365 – yeni bir kayıt oluştur**' a tıklayın veya dokunun.
9. **Kuruluş adı**altında, akışın kayıt oluşturmasını istediğiniz Dynamics 365 örneğini seçin. Olayın tetiklendiğine benzer bir örnek olması gerekmez.
10. **Varlık adı**altında, olay gerçekleştiğinde bir kayıt oluşturacak varlığı seçin.
    
     Bu izlenecek yol için **Görevler**' i seçin.
11. **Konu** kutusu görüntülenir. Bu alana tıkladığınızda veya dokunduğunuzda, bu alanlardan birini seçebileceğiniz bir dinamik içerik bölmesi görüntülenir.
    
    * **Soyadı**. Bu alanı seçerseniz, müşteri adayının soyadı, oluşturulduğu sırada görevin **Konu** alanına eklenir.
    * **Konusuna bakın**. Bu alanı seçerseniz, müşteri adayının **Konu** alanı oluşturulduğunda görevin **Konu** alanına eklenecektir.
    
    Bu izlenecek yol için **Konu**' yı seçin.
    
    ![Flow konu ekle](./media/connection-dynamics365/flow-addtopic.png)
    
    > **İpucu:** Varlıkla ilişkili daha fazla alan görüntülemek için dinamik içerik bölmesinde **daha fazla gör** ' e tıklayın veya dokunun. Örneğin, görevin **Konu** alanını da müşteri adayının **Şirket adı**, **Müşteri**, **Açıklama**veya **e-posta** alanıyla doldurabilirsiniz.
    > 
    > 
12. **Akış oluştur**' a tıklayın veya dokunun.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Dynamics 365 görevinden bir Wunderlist görevi oluşturma
Bu izlenecek yol, Dynamics 365 ' de bir görev oluşturulduğunda [Wunderlist](https://www.wunderlist.com) 'te bir görev oluşturmayı gösterir. Wunderlist, Yapılacaklar listeleri oluşturmak, anımsatıcılar eklemek veya Errand 'leri izlemek için kullanabileceğiniz bir Internet tabanlı hizmettir.

1. [Microsoft Flow web sitesinde](https://flow.microsoft.com/)oturum açın.
2. **Akışlarım**' a tıklayın veya dokunun ve ardından **boş oluştur**' a tıklayın veya dokunun.
3. Akış Tetikleyicileri listesinde, **bir kayıt oluşturulduğunda Dynamics 365-** ' ya tıklayın veya dokunun.
4. **Kuruluş adı**altında, akışın dinlemesini istediğiniz Dynamics 365 örneğini seçin.
5. **Varlık adı**altında, dinlemek istediğiniz varlığı seçin. Bu, akışı başlatmak için bir tetikleyici görevi görür.
   
    Bu izlenecek yol için **Görevler**' i seçin.
6. **Yeni adım**' a ve ardından **Eylem Ekle**' ye tıklayın veya dokunun.
7. *Bir görev oluşturun*yazın ve ardından **Wunderlist – görev oluştur**' a tıklayın veya dokunun.
8. **LISTE kimliği**altında **gelen kutusu**' nu seçin.
9. **Başlık**altında, dinamik Içerik bölmesinde **Konu** ' yı seçin.
10. **Akış oluştur**' a tıklayın veya dokunun.  

## <a name="trigger-based-logic"></a>Tetikleme tabanlı mantık
Bir kayıt **oluşturulduğunda**, **bir kayıt**güncelleştirilirken ve **bir kayıt silindiğinde** , olay gerçekleşen birkaç dakika içinde akışınızı başlatmak gibi tetikler.  Nadir durumlarda, akışınız tetiklemenin 2 saate kadar sürebilir.

Tetikleyici gerçekleştiğinde, akış bir bildirim alır, ancak akış, eylem çalıştığı sırada mevcut veriler üzerinde çalışır.  Örneğin, akışınız yeni bir kayıt oluşturulduğunda tetiklenir ve akışı çalıştırılmadan önce iki kez kaydı güncelleştirirseniz, akışınız en son verilerle yalnızca bir kez çalışır.

## <a name="specify-advanced-options"></a>Gelişmiş seçenekleri belirtin
Bir akışa adım eklediğinizde, verilerin akışta nasıl filtreleneceğini denetleyen bir filtre veya bir sorgu eklemek için **Gelişmiş seçenekleri göster** ' e tıklayabilirsiniz veya dokunun.

Örneğin, yalnızca etkin kişileri almak için bir filtre sorgusu kullanabilirsiniz ve bunları son ada göre sıralayabileceğiniz şekilde düzenleyebilirsiniz. Bunu yapmak için, bkz. OData filtre sorgusu **StatusCode EQ 1** ve dinamik Içerik bölmesinden **Soyadı** ' nı seçin. Sorgulara göre filtre ve sıralama hakkında daha fazla bilgi için bkz. [MSDN: $Filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) ve [MSDN: $OrderBy](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Akış orderby sorgusu](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Gelişmiş seçenekleri kullanırken en iyi uygulamalar
Bir alana bir değer eklediğinizde, bir değer yazarken veya dinamik içerik bölmesinden birini seçerek alan türüyle aynı olmalıdır.

| Alan türü | Nasıl kullanılır | Nerede bulunacak | Ada | Veri türü |
| --- | --- | --- | --- | --- |
| Metin alanları |Metin alanları, tek satırlık bir metin veya metin türü alanı olan dinamik içerik gerektirir. Örnek olarak **Kategori** ve **alt kategori** alanları bulunur. |**Ayarlar** > **özelleştirmeler** > **System** > **varlıklarını** özelleştirme > **görev** > **alanları** |**alan** |**Tek satırlık metin** |
| Tamsayı alanları |Bazı alanlar tamsayı türünde bir alan tamsayı veya dinamik içerik gerektirir. Örnek olarak tamamlanma **yüzdesi** ve **süre**dahildir. |**Ayarlar** > **özelleştirmeler** > **System** > **varlıklarını** özelleştirme > **görev** > **alanları** |**tamamlanmatamam** |**Tam sayı** |
| Tarih alanları |Bazı alanlar aa/gg/yyyy biçiminde girilmiş bir tarih veya bir tarih türü alanı olan dinamik içerik gerektirir. Örnek olarak **Oluşturulma**, **Başlangıç tarihi**, **gerçek başlangıç**, **son bekleme süresi**, **gerçek bitiş**ve son **Tarih**sayılabilir. |**Ayarlar** > **özelleştirmeler** > **System** > **varlıklarını** özelleştirme > **görev** > **alanları** |**createdon** |**Tarih ve saat** |
| Kayıt KIMLIĞI ve arama türü gerektiren alanlar |Başka bir varlık kaydına başvuruda bulunan bazı alanlar, hem kayıt KIMLIĞI hem de arama türü gerektirir. |**Ayarlar** > **özelleştirmeler** > **System** > **varlıklarını** > **Hesap** > **alanları** özelleştirme |**Accoun** |**Birincil anahtar** |
|Seçenek kümesi|Seçenek kümesi alanları, bu alan türüne geçirilecek bilinen bir tamsayı değeri gerektirir.  Dynamics 365 özelleştirme alanında, ilgili etiketle birlikte tamsayı ve yedekleme seçeneğini ayarlar.|Ayarlar > Özelleştirme > System > varlıklarını > Hesap > alanları özelleştirme | Tercih edilen Iletişim yöntemi| Tam sayı|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Kayıt KIMLIĞI ve arama türü gerektiren alanlara daha fazla örnek
Önceki tabloda genişleyen, dinamik içerik listesinden seçilen değerlerle çalışmayan alanlara daha fazla örnek verilmiştir. Bunun yerine, bu alanlar PowerApps 'teki alanlara girilen bir kayıt KIMLIĞI ve arama türü gerektirir.

* **Sahip** ve **sahip türü**.
  
  * **Sahip** alanı geçerli bir kullanıcı veya takım kayıt kimliği olmalıdır.
  * **Sahip türü** **systemusers** veya **takımlar**olmalıdır.
* **Müşteri** ve **Müşteri türü**.
  
  * **Müşteri** alanı geçerli bir hesap veya ilgili kışı kaydı kimliği olmalıdır.
  * **Müşteri türü** , **Hesap** veya **kişi**olmalıdır.
* **Ve** ilgili **türü**.
  
  * **İlgili** alan, hesap veya ilgili kışı kaydı kimliği gibi geçerli BIR kayıt kimliği olmalıdır.
  * **Ilgili tür** , kayıt için **Hesap** veya **kişi**gibi arama türü olmalıdır.

Bu örnek, kayıt KIMLIĞINE karşılık gelen bir hesap kaydını ekleyerek görevin **ilgili** alanına ekler.

  ![Flow recordID ve tür hesabı](./media/connection-dynamics365/flow-recordid-account.png)

Bu örnek ayrıca, kullanıcının kayıt KIMLIĞINE göre görevi belirli bir kullanıcıya atar.

  ![Flow kayıt kimliği ve Kullanıcı türü](./media/connection-dynamics365/flow-recordid-user.png)

Bir kaydın KIMLIĞINI bulmak için, bu konunun ilerleyen kısımlarında [kayıt kimliğini bulma](#find-the-records-id) bölümüne bakın.

> **Önemli:** "Yalnızca iç kullanım Için" açıklaması varsa alanlar bir değer içermemelidir. Bu alanlar, **çapraz yol**, **ek parametreler**ve **saat dilimi kuralı sürüm numarasını içerir.**
> 
> 

## <a name="find-the-records-id"></a>Kaydın KIMLIĞINI bulun
1. Dynamics 365 web uygulamasında, hesap kaydı gibi bir kayıt açın.
2. Eylemler araç çubuğunda, **açılan** ![
   öne kaydı](./media/connection-dynamics365/popout.png) ' na tıklayın veya dokunun (veya tam URL 'yi varsayılan e-posta programınıza kopyalamak için **bir bağlantıya** tıklayın veya dokunun).
   
    Web tarayıcısının adres çubuğunda URL,% 7B ve% 7d kodlama karakterleri arasındaki kayıt KIMLIĞINI içerir.
   
   ![Kayıt kimliği](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>İlgili konular
[Flow sorunlarını giderme](fix-flow-failures.md)

[Kuruluşunuzda akış Q &](organization-q-and-a.md)

[Sık sorulan sorular](frequently-asked-questions.md)

