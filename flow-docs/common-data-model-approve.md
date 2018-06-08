---
title: Common Data Service ile onay döngüsü oluşturma | Microsoft Docs
description: Gözden geçirenlerin Dropbox'a eklenen dosyaları onaylayabilmesi veya reddedebilmesi için birlikte çalışan bir varlık, akış ve uygulama oluşturun.
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
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: f56b109cc0263c8464d6d7475421ab32af8888d5
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "29351347"
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Microsoft Flow'u ve Microsoft Common Data Service'ı kullanarak bir onay döngüsü oluşturma
Common Data Service, bilgilerin akıştan bağımsız olarak bir veritabanında depolandığı akışlar oluşturmanızı sağlayabilir. Bunun en iyi örneği onaylardır. Onay durumunu bir varlıkta depolarsanız, ek olarak akışınız da çalışabilir.

Bu örnekte, kullanıcının Dropbox'a dosya eklemesiyle başlayan bir onay işlemi oluşturacaksınız. Dosya eklendiğinde, dosya ile ilgili bilgiler bir uygulamada görüntülenir. Burada, gözden geçirenler değişikliği onaylayıp reddedebilir. Gözden geçiren, değişikliği onayladığında veya reddettiğinde bildirim e-postası gönderilir ve reddedilen dosyalar Dropbox'tan silinir.

Bu bölümdeki adımları uygulayarak şunları oluşturacaksınız:

* Dropbox'a eklenen her dosyayla ilgili bilgilerin yanı sıra, dosyaların durumuyla (onaylandı, reddedildi veya beklemede) ilgili bilgiler içeren bir **özel varlık**.
* Dropbox'a bir dosya eklendiğinde özel varlığa bilgi ekleyen, dosya onaylandığında veya reddedildiğinde e-posta gönderen ve reddedilen dosyaları silen bir **akış**. Bu adımlarda bir akışı sıfırdan nasıl oluşturacağınız gösterilmektedir ancak bir şablon kullanarak da buna benzer bir akış oluşturabilirsiniz.
* gözden geçirenin, Dropbox'a eklenen dosyaları onaylayıp reddedebileceği bir **uygulama**. Bu uygulamayı, özel varlıkta bulunan alanlara göre otomatik olarak oluşturmak için PowerApps'i kullanacaksınız.

**Önkoşullar**

* [Microsoft Flow](sign-up-sign-in.md)’a ve [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/)'e kaydolun.
* [Bağlantılarınızı yönetme](https://powerapps.microsoft.com/tutorials/add-manage-connections/) bölümünde açıklanan şekilde, Dropbox ve Office 365 Outlook'a yönelik bağlantılar oluşturun.

## <a name="build-the-entity"></a>Varlığı oluşturma
1. [powerapps.com](https://web.powerapps.com)'da oturum açın.
2. Sol gezinti çubuğu varsayılan olarak görüntülenmezse sol üst köşede bulunan ve üç yatay çizgiden oluşan simgeye tıklayın veya dokunun.
   
    ![Sol gezinti çubuğunu açma](./media/common-data-model-approve/hamburger-icon.png)
3. Sol gezinti çubuğunda, **Yönet**'e ve ardından **Varlıklar**'a tıklayın veya dokunun.
   
    ![Varlıkları yönetme](./media/common-data-model-approve/manage-entities.png)
4. İstenirse **Veritabanımı oluştur**'a tıklayın veya dokunun.
   
    ![Veritabanı oluşturma](./media/common-data-model-approve/create-database.png)
5. Sağ üst köşenin yakınında bulunan **Yeni varlık**'a tıklayın veya dokunun.
   
    ![Varlık oluşturma](./media/common-data-model-approve/new-entity.png)
   
    Tarayıcı pencereniz ekranı kaplamıyorsa bu düğme farklı bir yerde görünebilir.
6. **Varlık adı** alanında, boşluk içermeyen ve veritabanınızdaki diğer varlık adlarından farklı bir ad belirtin.
   
    Bu örneği tümüyle uygulamak için, adı **ReviewDropboxFiles** olarak belirtin.
   
    ![Varlık adı belirtme](./media/common-data-model-approve/entity-name.png)
7. **Görünen ad** alanında bir kolay ad belirtin.
   
    ![Görünen ad belirtme](./media/common-data-model-approve/display-name.png)
8. **İleri**'ye tıklayın veya dokunun.
   
    ![İleri düğmesi](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Varlığa alan ekleme
1. Sağ üst köşede bulunan **Alan ekle**'ye tıklayın veya dokunun.
   
    ![Alan ekleme](./media/common-data-model-approve/add-field.png)
2. Alanlar listesinin en altında görünen boş satırda, **Approver** alanının özelliklerini ayarlayın. (Bu özellikleri ayarladıktan sonra Tab tuşuna basarak bir sonraki sütuna geçebilirsiniz.)
   
   * **Görünen Ad** sütununa **Approver** (Onaylayan) yazın.
   * **Ad** sütununa **ApproverEmail** (Onaylayan E-postası) yazın.
   * **Tür** sütununda **Email** (E-posta) seçeneğine tıklayın veya dokunun.
   * **Gerekli** sütununda onay kutusunu seçin.
     
     ![Approver (Onaylayan) alanı](./media/common-data-model-approve/approver-field.png)
3. Bir sonraki satırda, **Status** (Durum) alanının özelliklerini ayarlayın:
   
   * **Görünen Ad** sütununa **Status** (Durum) yazın.
   * **Ad** sütununa **Status** (Durum) yazın.
   * **Tür** sütununda, **Text** (Metin) seçeneğine tıklayın veya dokunun.
   * **Özellikler** sütununda varsayılan değeri bırakın.
   * **Gerekli** sütununda onay kutusunu seçin.
     
     ![Status (Durum) alanı](./media/common-data-model-approve/status-field.png)
4. Bir sonraki satırda, **FileID** (Dosya kimliği) alanının özelliklerini ayarlayın:
   
   * **Görünen Ad** sütununa **File identifier** (Dosya tanımlayıcısı) yazın.
   * **Ad** sütununa **FileID** (Dosya kimliği) yazın.
   * **Tür** sütununda, **Text** (Metin) seçeneğine tıklayın veya dokunun.
   * **Özellikler** sütununda varsayılan değeri bırakın.
   * **Benzersiz** sütununda onay kutusunu seçin.
   * **Gerekli** sütununda onay kutusunu seçin.
     
     ![FileID alanı](./media/common-data-model-approve/fileid-field.png)
5. **FileID** (Dosya kimliği) alanı için sağ kenardaki üç noktaya (...) ve ardından **Başlık alanı olarak ayarla**'ya tıklayın veya dokunun.
   
    ![Başlık alanı ayarlama](./media/common-data-model-approve/set-title-field.png)
6. Sol alt köşedeki **Oluştur**'a tıklayın veya dokunun.
   
    ![Varlık oluşturma](./media/common-data-model-approve/create-button.png)
7. (isteğe bağlı) Varlıklar listesi yeniden görüntülendiğinde, ekranı kaplamıyorsa tarayıcı pencerenize ekranı kaplatın ve ardından **Tür** sütun başlığına tıklayın veya dokunun. Liste, özel varlıklar (az önce oluşturduğunuz varlık gibi) üstte görüntülenecek şekilde sıralanır.

## <a name="sign-in-and-create-a-flow"></a>Oturum açma ve akış oluşturma
1. [Microsoft Flow portalını](https://flow.microsoft.com) açın.
2. Ekranı kaplamıyorsa, tarayıcı pencerenize ekranı kaplatın ve ardından sağ üst köşede bulunan **Oturum aç**'a tıklayın veya dokunun.
   
    ![Microsoft Flow için oturum açma düğmesi](./media/common-data-model-approve/signin-flow.png)
3. Sağ üst köşedeki menüden, powerapps.com’da veritabanını oluşturduğunuz ortamı seçersiniz.
   
    **Not**: Aynı ortamı seçmezseniz varlığınızı göremezsiniz.
4. Sol üst köşenin yakınında bulunan **Akışlarım**'a tıklayın veya dokunun.
   
    ![Akışlarım düğmesi](./media/common-data-model-approve/myflows-button.png)
5. Sağ üst köşenin yakınında bulunan **Yeni akış oluştur**'a tıklayın veya dokunun.
   
    ![Yeni akış oluştur düğmesi](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Dosya eklendiğinde başlama
1. **Daha fazla tetikleyici arayın** yazılı kutuya **Dropbox** yazın veya yapıştırın ve ardından **Dropbox - Bir dosya oluşturulduğunda**'ya tıklayın veya dokunun.
   
    ![Tetikleyici oluşturma](./media/common-data-model-approve/create-trigger.png)
2. **Klasör** alanında klasör simgesine tıklayın veya dokunun ve ardından dosyaların ekleneceği klasöre göz atın.
   
    ![Klasör seçme](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Varlığa veri ekleme
1. **Yeni adım**'a ve ardından **Eylem ekle**'ye tıklayın veya dokunun.
   
    ![Eylem ekleme](./media/common-data-model-approve/add-action.png)
2. **Daha fazla eylem arayın** yazılı kutuya **Common Data Service** yazın veya yapıştırın, ardından **Common Data Service - Nesne oluştur**'a tıklayın ya da dokunun.
   
    ![Common Data Service'ta nesne oluşturma](./media/common-data-model-approve/cdm-create-object.png)
3. **The entity** (Varlık) alanına **Review** (Gözden geçir) yazın veya yapıştırın ve ardından **Review Dropbox files**'a.(Dropbox dosyalarını gözden geçir) tıklayın veya dokunun.
   
    ![Varlığı seçme](./media/common-data-model-approve/choose-entity-flow.png)
4. **Title** (Başlık) alanında, kutuya tıklayın veya dokunun ve ardından parametre belirteçleri listesindeki **Dosya adı**'na tıklayarak veya dokunarak bu belirteci alana ekleyin.
   
    ![Dosya adı belirteci ekleme](./media/common-data-model-approve/add-filename-token.png)
5. **Approver** (Onaylayan) alanına, dosyaları gözden geçirecek kişinin e-posta adresini yazın veya yapıştırın.
   
    **Not**: Akışı test etme işlemini daha kolay hale getirmek için kendi adresinizi belirtin. Bunu, daha sonra akış gerçek kullanım için hazır olduğunda değiştirebilirsiniz.
   
    ![Onaylayan ekleme](./media/common-data-model-approve/add-approver.png)
6. **Status** (Durum) alanına **Pending** (Beklemede) yazın veya yapıştırın.
   
    ![Varsayılan durum ekleme](./media/common-data-model-approve/add-default-status.png)
7. **File identifier** (Dosya Tanımlayıcısı) alanında, kutuya tıklayın veya dokunun ve ardından parametre belirteçleri listesindeki **Dosya tanımlayıcısı**'na tıklayarak veya dokunarak bu belirteci alana ekleyin.
   
    ![Dosya tanımlayıcısı belirteci ekleme](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Dosyanın gözden geçirilip geçirilmediğini denetleme
1. **Create object** (Nesne oluştur) eyleminin altında; **Yeni adım**'a, ardından **Daha fazla**'ya ve **Do until ekle**'ye tıklayın veya dokunun.
   
    ![Do until ekleme](./media/common-data-model-approve/add-do-until.png)
2. **Do until** eyleminin sol üst köşesinde, **Bir değer seçin** yazılı kutuya tıklayın veya dokunun.
   
    ![Değer seçme](./media/common-data-model-approve/choose-value.png)
   
    **Not**: Tarayıcı pencereniz ekranı kaplamıyorsa **Bir değer seçin** yazılı üst kutuya tıklayın veya dokunun.
3. **Create object çıkışları** (Nesne oluştur çıkışları) altında bulunan **Status**'a (Durum) tıklayarak veya dokunarak bu parametre belirtecini alana ekleyin.
   
    ![Status (Durum) belirteci ekleme](./media/common-data-model-approve/add-status.png)
4. **Do until** eyleminin ortasında bulunan listeyi açın ve ardından **eşit değildir**'e tıklayın veya dokunun.
   
    ![Eşit değildir belirtme](./media/common-data-model-approve/is-not-equal.png)
5. **Do until** eyleminin sağ üst köşesinde, **Bir değer seçin** yazılı kutuya **Pending** (Beklemede) yazın veya yapıştırın.
   
    ![İzlenecek durumu belirtin](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Not**: Tarayıcı pencereniz ekranı kaplamıyorsa **Bir değer seçin** yazılı alt kutuya tıklayın veya dokunun.
6. **Do until** eyleminin altındaki **Eylem ekle**'ye tıklayın veya dokunun.
   
    ![Do until'e eylem ekleme](./media/common-data-model-approve/add-action-in-dountil.png)
7. **Daha fazla eylem arayın** yazılı kutuya **Common** yazın ve ardından **Common Data Service - Nesne al**'a tıklayın veya dokunun.
   
    ![Nesne alma](./media/common-data-model-approve/get-object.png)
8. **The namespace** (Ad alanı) alanında, veritabanınıza tıklayın veya dokunun.
9. **The entity** (Varlık) alanına **Review** (Gözden geçir) yazın veya yapıştırın ve ardından **Review Dropbox files**'a.(Dropbox dosyalarını gözden geçir) tıklayın veya dokunun.
   
    ![Varlık seçme](./media/common-data-model-approve/choose-entity-flow.png)
10. **Object id** (Nesne kimliği) alanında, kutuya tıklayın veya dokunun ve ardından **Dosya tanımlayıcısı** parametre belirtecine tıklayarak veya dokunarak alana ekleyin.
    
     ![Nesne tanımlayıcısı ekleme](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Öğenin onaylanıp onaylanmadığını denetleme
1. **Do-Until** eyleminin altında bulunan **Yeni adım**'a ve ardından **Koşul ekle**'ye tıklayın veya dokunun.
   
    ![Koşul ekleme](./media/common-data-model-approve/add-condition.png)
2. Koşulun sol üst köşesinde, **Bir değer seçin** yazılı kutuya tıklayın veya dokunun.
   
    ![Koşulun sol üst köşesi](./media/common-data-model-approve/condition-upper-left.png)
   
    **Not**: Tarayıcı pencereniz ekranı kaplamıyorsa **Bir değer seçin** yazılı üst kutuya tıklayın veya dokunun.
3. **Get object çıkışları** (Nesne al çıkışları) altında yer alan **Status** (Durum) parametre belirtecini alana eklemek için üzerine tıklayın veya dokunun.
   
    ![Koşula durum ekleme](./media/common-data-model-approve/add-status-to-condition.png)
4. Koşulun sağ üst köşesinde, **Bir değer seçin** yazılı kutuya **Approved** (Onaylandı) yazın veya kopyalayın.
   
    ![Durumun onaylandı olarak ayarlandığını doğrulayın](./media/common-data-model-approve/status-equals-approved.png)
   
    **Not**: Tarayıcı pencereniz ekranı kaplamıyorsa **Bir değer seçin** yazılı alt kutuya **Approved** (Onaylandı) yazın veya yapıştırın.

## <a name="send-notification-mail"></a>Bildirim e-postası gönderme
1. **Evet ise, hiçbir şey yapma**'nın altında bulunan **Eylem ekle**'ye tıklayın veya dokunun.
   
    ![Evet ise eylem ekleme](./media/common-data-model-approve/if-yes-action.png)
2. **Daha fazla eylem arayın** yazılı kutuya **e-posta gönder** yazın veya yapıştırın ve ardından **Office 365 Outlook - E-posta gönder**'e tıklayın veya dokunun.
   
    ![Evet ise e-posta gönder](./media/common-data-model-approve/if-yes-send-mail.png)
3. **Kime** alanına, bir öğe onaylandığında bildirim almasını istediğiniz kullanıcının adresini yazın veya yapıştırın.
   
    **Not**: Akışı test etme işlemini daha kolay hale getirmek için kendi adresinizi belirtin. Bunu, akış gerçek kullanım için hazır olduğunda değiştirebilirsiniz.
   
    ![Onay alıcısı](./media/common-data-model-approve/approval-recipient.png)
4. **Konu** altındaki kutuya tıklayın ve ardından **Dosya adı** parametre belirtecini alana eklemek için üzerine tıklayın veya dokunun.
   
    ![Dosya adını e-posta konusu olarak belirtme](./media/common-data-model-approve/subject-is-file-name.png)
5. **Gövde**'nin altına **Öğe onaylandı** yazın veya yapıştırın.
   
    ![Onay e-postası gövdesi](./media/common-data-model-approve/approval-body.png)
6. **Hayır ise, hiçbir şey yapma**'nın altında e-posta iletisinin gövdesini **Öğe reddedildi** olarak belirtmek dışında bu yordamın 1-5 adımlarını yineleyin.
   
    ![Reddetme e-postası gövdesi](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Reddedilen dosyaları silme
1. Reddetme e-postası alanları altındaki **Eylem ekle**'ye tıklayın veya dokunun.
   
    ![Silme eylemi ekleme](./media/common-data-model-approve/add-delete-action.png)
2. **Daha fazla eylem arayın** yazılı kutuya **Dropbox** yazın veya yapıştırın ve ardından **Dropbox - Dosyayı sil**'e tıklayın veya dokunun.
   
    ![Dropbox'tan dosya silme](./media/common-data-model-approve/dropbox-delete-file.png)
3. **Dosya**'nın altındaki kutuya tıklayın veya dokunun ve ardından **Dosya tanımlayıcısı** parametre belirtecini alana eklemek için üzerine tıklayın veya dokunun.
   
    ![Silinecek dosyayı tanımlama](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Akışı kaydetme
1. Ekranın üstünde, oluşturmakta olduğunuz akış için bir ad yazın veya yapıştırın ve ardından **Akış Oluştur**'a tıklayın veya dokunun.
   
    ![Akışı kaydetme](./media/common-data-model-approve/save-flow.png)
2. **Kapat**'a ve ardından **Bitti**'ye tıklayın veya dokunun.
3. Dropbox'ta belirttiğiniz klasöre, biri onayı diğeri ise reddi test etmek için kullanılacak şekilde en az iki dosya ekleyin.

## <a name="build-the-app"></a>Uygulamayı oluşturma
1. [powerapps.com](https://web.powerapps.com)'da oturum açın ve ardından sol gezinti çubuğunun altında bulunan **Yeni uygulama**'ya tıklayın veya dokunun.
   
    ![Tarayıcıda uygulama oluşturma](./media/common-data-model-approve/new-app-button.png)
2. Görüntülenen iletişim kutusunda, Windows için PowerApps Studio veya Web için PowerApps Studio'dan birini açma seçeneğine tıklayın veya dokunun.
3. Windows için PowerApps Studio'yu açtıysanız sol gezinti çubuğunda.bulunan **Yeni**'ye tıklayın veya dokunun.
4. **Verilerinizden uygulama oluşturun** altında, **Common Data Service** kutucuğunda bulunan **Telefon düzeni**'ne tıklayın veya dokunun.
   
    ![Uygulama oluşturma](./media/common-data-model-approve/afd-cdm.png)
5. **Search** (Ara) kutusuna **Review** (Gözden geçir) yazın veya yapıştırın.
   
    ![Varlık arama](./media/common-data-model-approve/search-entities.png)
6. **Choose an entity** (Varlık seçin) altında, **Review Dropbox Files**'a (Dropbox Dosyalarını Gözden Geçir) tıklayın veya dokunun.
   
    ![Varlık seçme](./media/common-data-model-approve/choose-entity.png)
7. Sağ alt köşenin yakınında bulunan **Connect**'e (Bağlan) tıklayın veya dokunun.
   
    ![Connect (Bağlan) düğmesi](./media/common-data-model-approve/connect-button.png)
8. Tanıtım turunun açılış ekranı görüntülenirse PowerApps'i daha yakından tanımak için turu başlatın.(veya **Skip**'e (Atla) tıklayın veya dokunun).
   
    ![Tanıtım turu](./media/common-data-model-approve/quick-tour.png)
   
    Sol üst köşenin yakınında bulunan soru işareti simgesine ve ardından **Take the intro tour**'a (Tanıtım turuna katıl) tıklayarak veya dokunarak tura daha sonra istediğiniz zaman katılabilirsiniz.
9. (isteğe bağlı) Ekranın alt kısmında bulunan kaydırıcıyı sürükleyerek uygulamayı daha kolay bir şekilde görebilirsiniz.
   
    ![Yakınlaştırma denetimi](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Uygulamayı özelleştirme
1. Sağ gezinti çubuğunda, bir başlık ve açıklama içeren düzene tıklayın veya dokunun.
   
    ![Connect (Bağlan) düğmesi](./media/common-data-model-approve/choose-layout.png)
2. **BrowseScreen** alanında, daha büyük metin kutusu denetimini seçmek için arama çubuğunun tam altına tıklayın veya dokunun.
   
    ![Başlık seçme](./media/common-data-model-approve/select-header.png)
3. Sağ bölmede, daha altta bulunan listenin aşağı okuna tıklayarak veya dokunarak listeyi açın.
   
    ![Açılan listeyi açma](./media/common-data-model-approve/open-dropdown.png)
4. Daha altta bulunan listede, eklenen dosyaların dosya adlarını görüntülemek için **Title**'a (Başlık) tıklayın veya dokunun.
   
    ![Başlık verilerini ayarlama](./media/common-data-model-approve/set-heading.png)
5. Sağ bölmede, daha üstte bulunan listeyi açın ve ardından her bir dosyanın durumunu görüntülemek için **Status**'a (Durum) tıklayın veya dokunun.
   
    ![Gövde verilerini ayarlama](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Genel çözümü test etme
1. PowerApps'te, sol üst köşede bulunan oynat düğmesine tıklayarak veya dokunarak Önizleme modunu açın.
   
    ![Önizleme modunu açma](./media/common-data-model-approve/open-preview.png)
2. Listedeki ilk dosya ile ilgili ayrıntıları görüntülemek için oka tıklayın veya dokunun.
   
    ![Ayrıntılar ekranını açma](./media/common-data-model-approve/open-details.png)
3. Sağ üst köşede, dosya ile ilgili ayrıntıları değiştirmek için kalem simgesine tıklayın veya dokunun.
   
    ![Düzenleme ekranını açma](./media/common-data-model-approve/edit-record.png)
4. **Status** (Durum) kutusuna **Approved** (Onaylandı) yazın veya yapıştırın.
   
    ![Bir dosyayı onaylama](./media/common-data-model-approve/change-status.png)
5. Sağ üst köşede, değişikliklerinizi kaydedip ayrıntılar ekranına dönmek için onay işareti simgesine tıklayın veya dokunun.
   
    ![Değişiklikleri kaydetme](./media/common-data-model-approve/save-record.png)
   
    Birkaç dakika içinde dosyanın onaylandığını bildiren bir e-posta alırsınız.
6. Gözatma ekranına dönmek için sağ üst köşede bulunan geri düğmesine tıklayın veya dokunun.
   
    ![Gözatma ekranına dönme](./media/common-data-model-approve/back-arrow.png)
7. Listedeki diğer dosya ile ilgili ayrıntıları görüntülemek için oka tıklayın veya dokunun.
   
    ![Ayrıntılar ekranını açma](./media/common-data-model-approve/open-details.png)
8. Sağ üst köşede, dosya ile ilgili ayrıntıları değiştirmek için kalem simgesine tıklayın veya dokunun.
   
    ![Düzenleme ekranını açma](./media/common-data-model-approve/edit-record.png)
9. **Status** (Durum) kutusuna **Rejected** (Reddedildi) (veya **Aproved** ya da **Approoved** da dahil olmak üzere **Approved** (Onaylandı) dışında herhangi bir ifade) yazın veya yapıştırın.
   
    ![Dosyayı reddetme](./media/common-data-model-approve/reject-file.png)
10. Sağ üst köşede, değişikliklerinizi kaydedip ayrıntılar ekranına dönmek için onay işareti simgesine tıklayın veya dokunun.
    
     ![Değişiklikleri kaydetme](./media/common-data-model-approve/save-record.png)
    
     Birkaç dakika içinde dosyanın reddedildiğini ve dosyanın Dropbox'tan silineceğini belirten bir e-posta alırsınız.

