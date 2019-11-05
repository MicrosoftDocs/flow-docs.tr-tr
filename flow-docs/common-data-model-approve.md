---
title: Common Data Service bir onay döngüsü oluşturun | Microsoft Docs
description: Gözden geçirenlerin Dropbox 'a eklenen dosyaları onaylamasını veya reddedebilmesi için birlikte çalışan bir varlık, akış ve uygulama oluşturun.
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4f58e5b3095769349e71e9ba8b203ea678981391
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546842"
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Microsoft Flow ve Microsoft Common Data Service kullanarak bir onay döngüsü oluşturun
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Common Data Service, bir akıştan bağımsız olarak bir veritabanında depolanan bilgiler içeren akışlar oluşturmak için bir yol sağlayabilir. Bunun en iyi örneği onaylarla aynıdır. Onay durumunu bir varlıkta depolarsanız, akışınız üzerinde çalışabilir.

Bu örnekte, bir Kullanıcı Dropbox 'a dosya eklediğinde başlayan bir onay işlemi oluşturacaksınız. Dosya eklendiğinde, bir gözden geçirenin değişikliği onaylayabileceği veya reddedebildiği bir uygulamada, onunla ilgili bilgiler görüntülenir. Gözden geçiren değişikliği onayladığında veya reddettiğinde, bildirim postası gönderilir ve reddedilen dosyalar Dropbox 'tan silinir.

Bu bölümdeki adımları izleyerek şunları oluşturacaksınız:

* Dropbox 'a eklenen her dosya ve dosyanın durumunun onaylanmış, reddedildi veya beklemede olup olmadığı hakkında bilgi içeren **özel bir varlık** .
* Dropbox 'a bir dosya eklendiğinde özel varlığa bilgi ekleyen bir **akış** , Dosya onaylandığında veya reddedildiğinde e-posta gönderir ve reddedilen dosyaları siler. Bu adımlarda, bu tür bir akışın sıfırdan nasıl oluşturulacağı gösterilmektedir, ancak şablondan benzer bir akış oluşturabilirsiniz.
* Gözden geçirenin Dropbox 'a eklenen dosyaları onaylayabileceği veya reddedebileceği bir **uygulama** . Bu uygulamayı özel varlıktaki alanlara göre otomatik olarak oluşturmak için PowerApps 'i kullanacaksınız.

**Kaynakları**

* [Microsoft Flow](sign-up-sign-in.md) ve [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/)'e kaydolun.
* [Bağlantılarınızın](https://powerapps.microsoft.com/tutorials/add-manage-connections/) açıklandığı şekilde Dropbox ve Office 365 Outlook bağlantıları oluşturun.

## <a name="build-the-entity"></a>Varlığı oluşturma
1. [PowerApps.com](https://web.powerapps.com)'de oturum açın.
2. Sol gezinti çubuğu varsayılan olarak görünmezse, sol üst köşedeki üç yatay çizgi ile simgeye tıklayın veya dokunun.
   
    ![Sol gezinti çubuğunu aç](./media/common-data-model-approve/hamburger-icon.png)
3. Sol gezinti çubuğunda, **Yönet**' e ve ardından **varlıklar**' a tıklayın veya dokunun.
   
    ![Varlıkları Yönet](./media/common-data-model-approve/manage-entities.png)
4. İstenirse **veritabanımı oluştur**' a tıklayın veya dokunun.
   
    ![Veritabanı oluştur](./media/common-data-model-approve/create-database.png)
5. Sağ üst köşedeki **yeni varlık**' a tıklayın veya dokunun.
   
    ![Varlık oluştur](./media/common-data-model-approve/new-entity.png)
   
    Tarayıcı pencereniz ekranı kaplamıyorsa, bu düğme farklı bir yerde görünebilir.
6. **Varlık adı**altında, boşluk içermeyen ve veritabanınızda başka bir varlık olmayan bir ad belirtin.
   
    Bu örneği tam olarak izlemek için, **Belgelerdropboxfiles**' ı belirtin.
   
    ![Varlık adını belirtin](./media/common-data-model-approve/entity-name.png)
7. **Görünen ad**' ın altında, bir kolay ad belirtin.
   
    ![Görünen ad belirtin](./media/common-data-model-approve/display-name.png)
8. **İleri**' ye tıklayın veya dokunun.
   
    ![İleri düğmesi](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Varlığa alan ekleme
1. Sağ üst köşedeki **alan Ekle**' ye tıklayın veya dokunun.
   
    ![Alan Ekle](./media/common-data-model-approve/add-field.png)
2. Alan listesinin en altında görünen boş satırda, **onaylayan** alanının özelliklerini ayarlayın. (Bu özellikleri ayarlarsanız Tab tuşuna basarak bir sonraki sütuna geçebilirsiniz.)
   
   * **Görünen ad** sütununda **onaylayan**yazın.
   * **Ad** sütununda **approveremail**yazın.
   * **Tür** sütununda **e-posta** seçeneğine tıklayın veya dokunun.
   * **Gerekli** sütununda onay kutusunu seçin.
     
     ![Onaylayan alanı](./media/common-data-model-approve/approver-field.png)
3. Bir sonraki satırda, bir **durum** alanının özelliklerini ayarlayın:
   
   * **Görünen ad** sütununda **durum**yazın.
   * **Ad** sütununda **durum**yazın.
   * **Tür** sütununda, **metin** seçeneğine tıklayın veya dokunun.
   * **Özellikler** sütununda, varsayılan değeri bırakın.
   * **Gerekli** sütununda onay kutusunu seçin.
     
     ![Durum alanı](./media/common-data-model-approve/status-field.png)
4. Sonraki satırda, bir **FileId** alanının özelliklerini ayarlayın:
   
   * **Görünen ad** sütununda **dosya tanımlayıcısı**yazın.
   * **Ad** sütununa **FileId**yazın.
   * **Tür** sütununda, **metin** seçeneğine tıklayın veya dokunun.
   * **Özellikler** sütununda, varsayılan değeri bırakın.
   * **Benzersiz** sütununda onay kutusunu seçin.
   * **Gerekli** sütununda onay kutusunu seçin.
     
     ![FileId alanı](./media/common-data-model-approve/fileid-field.png)
5. Sağ kenarda, **FileId** alanı için üç nokta işaretine (...) ve ardından **başlık alanı olarak ayarla**' ya tıklayın veya dokunun.
   
    ![Başlık alanını ayarla](./media/common-data-model-approve/set-title-field.png)
6. Sol alt köşedeki **Oluştur**' a tıklayın veya dokunun.
   
    ![Varlık oluşturma](./media/common-data-model-approve/create-button.png)
7. seçim Varlıkların listesi yeniden görüntülenirse, zaten ekranı kaplamıyorsa tarayıcı pencerenizi en üst düzeye çıkarın ve ardından **tür** sütun başlığına tıklayın veya dokunun. Liste, az önce oluşturduğunuz ve en üstte görünen özel varlıklarla sıralanır.

## <a name="sign-in-and-create-a-flow"></a>Oturum açın ve akış oluşturun
1. [Microsoft Flow portalını](https://flow.microsoft.com)açın.
2. Zaten ekranı kaplamamışsa tarayıcı pencerenizi en üst düzeye çıkarın ve sağ üst köşedeki **oturum aç** ' a tıklayın veya dokunun.
   
    ![Microsoft Flow için oturum açma düğmesi](./media/common-data-model-approve/signin-flow.png)
3. Sağ üst taraftaki menüde, powerapps.com 'de veritabanını oluşturduğunuz ortamı seçersiniz.
   
    **Not**: aynı ortamı seçmezseniz, varlığınızı görmezsiniz.
4. Sol üst köşenin yakınında bulunan **Akışlarım**' a tıklayın veya dokunun.
   
    ![Akışlarım düğmesi](./media/common-data-model-approve/myflows-button.png)
5. Sağ üst köşenin yakınında **Yeni akış oluştur**' a tıklayın veya dokunun.
   
    ![Yeni akış oluştur düğmesi](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Bir dosya eklendiğinde Başlat
1. **Daha fazla tetikleyici ara**' yı Içeren kutuya **Dropbox**yazın veya yapıştırın ve ardından **Dropbox-bir dosya oluşturulduğunda**ya da dokunun.
   
    ![Tetikleyici oluştur](./media/common-data-model-approve/create-trigger.png)
2. **Klasör**' ün altında, klasör simgesine tıklayın veya dokunun ve ardından dosyaların ekleneceği klasöre gidin.
   
    ![Klasör Seç](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Varlığa veri ekleme
1. **Yeni adım**' a ve ardından **Eylem Ekle**' ye tıklayın veya dokunun.
   
    ![Eylem ekleme](./media/common-data-model-approve/add-action.png)
2. **Daha fazla eylem ara**' yı içeren kutuya **Common Data Service**yazın veya yapıştırın ve ardından **Common Data Service-nesne oluştur**' a tıklayın veya dokunun.
   
    ![Common Data Service bir nesne oluşturun](./media/common-data-model-approve/cdm-create-object.png)
3. **Varlık**altında, **Gözden geçirme**yazın veya yapıştırın ve ardından **Dropbox dosyalarını gözden geçir**' e tıklayın veya dokunun.
   
    ![Varlığı seçin](./media/common-data-model-approve/choose-entity-flow.png)
4. **Başlık**' ın altında, kutuya tıklayın veya dokunun ve ardından bu belirteci alana eklemek için parametre belirteçleri listesindeki **dosya adı** ' na tıklayın veya dokunun.
   
    ![Dosya adı belirteci Ekle](./media/common-data-model-approve/add-filename-token.png)
5. **Onaylayan**altında, dosyaları gözden geçibileceğiniz kişinin e-posta adresini yazın veya yapıştırın.
   
    **Unutmayın**: akışın sınamasını daha kolay hale getirmek için kendi adresinizi belirtin. Daha sonra, akış fiili kullanım için hazırlandığınızda bu işlemi değiştirebilirsiniz.
   
    ![Onaylayan Ekle](./media/common-data-model-approve/add-approver.png)
6. **Durum**' ın altında, **bekleyen**yazın veya yapıştırın.
   
    ![Varsayılan durum Ekle](./media/common-data-model-approve/add-default-status.png)
7. **Dosya tanımlayıcısı**' nın altında, kutuya tıklayın veya dokunun ve ardından bu belirteci alana eklemek için parametre belirteçleri listesindeki **dosya tanımlayıcısı** ' na tıklayın veya dokunun.
   
    ![Dosya tanımlayıcı belirteci Ekle](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Dosyanın gözden geçirilip geçirilmediğini denetleyin
1. **Nesne oluştur** eyleminin altında **yeni adım**' a tıklayın veya dokunun, **daha fazla**' ya tıklayın veya dokunun ve ardından işlem **Ekle**' ye tıklayın veya dokunun.
   
    ![Ekle](./media/common-data-model-approve/add-do-until.png)
2. **Do Until** eyleminin sol üst köşesinde, **bir değer seçin**' in bulunduğu kutuya tıklayın veya dokunun.
   
    ![Bir değer seçin](./media/common-data-model-approve/choose-value.png)
   
    **Note**: tarayıcı pencereniz ekranı kaplamıyorsa, **bir değer seçin**' in bulunduğu üstteki kutuya tıklayın veya dokunun.
3. **Nesne oluştur**' un altında, bu parametre belirtecini alana eklemek için **durum** ' a tıklayın veya dokunun.
   
    ![Durum belirteci Ekle](./media/common-data-model-approve/add-status.png)
4. **Do Until** eyleminin merkezinin yakınında bulunan listeyi açın ve ardından **eşit değildir**' e tıklayın veya dokunun.
   
    ![Şuna eşit değildir belirt](./media/common-data-model-approve/is-not-equal.png)
5. **Do Until** eyleminin sağ üst köşesinde, **bir değer seçin**' in bulunduğu kutuya **bekleyen** yazın veya yapıştırın.
   
    ![İzlenecek durumu belirtin](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Note**: tarayıcı pencereniz ekranı kaplamıyorsa, **bir değer seçin**' in bulunduğu alt kutuya tıklayın veya dokunun.
6. **Yapılacaklar** eyleminin alt kısmına yakın **bir eylem Ekle**' ye tıklayın veya dokunun.
   
    ![Eyleme işlem Ekle](./media/common-data-model-approve/add-action-in-dountil.png)
7. **Daha fazla eylem ara**' yı Içeren kutuya **ortak**yazın ve ardından **Common Data Service-nesne al**' a tıklayın veya dokunun.
   
    ![Bir nesne al](./media/common-data-model-approve/get-object.png)
8. **Ad alanı**altında veritabanınıza tıklayın veya dokunun.
9. **Varlık**altında, **Gözden geçirme**yazın veya yapıştırın ve ardından **Dropbox dosyalarını gözden geçir**' e tıklayın veya dokunun.
   
    ![Varlık Seç](./media/common-data-model-approve/choose-entity-flow.png)
10. **Nesne kimliği**' nin altında, kutuya tıklayın veya dokunun ve ardından alana eklemek için **dosya tanımlayıcısı** parametre belirtecine tıklayın veya dokunun.
    
     ![Nesne tanımlayıcısı Ekle](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Öğenin onaylanıp onaylanmadığını denetleyin
1. **Do-Until** eyleminin altında, **yeni adım**' a ve ardından **Koşul Ekle**' ye tıklayın veya dokunun.
   
    ![Koşul Ekle](./media/common-data-model-approve/add-condition.png)
2. Koşulun sol üst köşesinde, **bir değer seçin**' in bulunduğu kutuya tıklayın veya dokunun.
   
    ![Koşulun sol üst köşesi](./media/common-data-model-approve/condition-upper-left.png)
   
    **Note**: tarayıcı pencereniz ekranı kaplamıyorsa, **bir değer seçin**' in bulunduğu üstteki kutuya tıklayın veya dokunun.
3. **Get nesnesinden çıktılar**altında, alana eklemek için **durum** parametresinin simgesine tıklayın veya dokunun.
   
    ![Koşula durum ekleme](./media/common-data-model-approve/add-status-to-condition.png)
4. Koşulun sağ üst köşesinde, **bir değer seçin**' in bulunduğu kutuya **onaylanmış** yazın veya yapıştırın.
   
    ![Durumun Onaylandı olarak ayarlandığını doğrulayın](./media/common-data-model-approve/status-equals-approved.png)
   
    **Note**: tarayıcı pencereniz ekranı kaplamıyorsa, **bir değer seçin**' ın bulunduğu alt kutuya **onaylanmış** yazın veya yapıştırın.

## <a name="send-notification-mail"></a>Bildirim postası gönder
1. **Evet ise, hiçbir şey yapmayın**, **Eylem Ekle**' ye tıklayın veya dokunun.
   
    ![Yanıt Evet ise, bir eylem ekleyin](./media/common-data-model-approve/if-yes-action.png)
2. **Daha fazla eylem ara**' yı içeren kutuya **posta gönder**yazın veya yapıştırın ve ardından **Office 365 Outlook-e-posta gönder ' e**tıklayın veya dokunun.
   
    ![Yanıt Evet ise, posta gönder](./media/common-data-model-approve/if-yes-send-mail.png)
3. ' **In**altında, bir öğe kabul edildiğinde bildirmek istediğiniz kişinin adresini yazın veya yapıştırın.
   
    **Unutmayın**: akışın sınamasını daha kolay hale getirmek için kendi adresinizi belirtin. Akış, fiili kullanım için hazırsa bunu değiştirebilirsiniz.
   
    ![Onay alıcısı](./media/common-data-model-approve/approval-recipient.png)
4. **Konu**' ın altında, kutuya tıklayın veya dokunun ve ardından alana eklemek için **dosya adı** parametre belirtecine tıklayın veya dokunun.
   
    ![E-posta konusu olarak dosya adını belirtin](./media/common-data-model-approve/subject-is-file-name.png)
5. **Gövde**' ın altında, **öğe onaylanmış** olarak yazın veya yapıştırın.
   
    ![Onay e-postası gövdesi](./media/common-data-model-approve/approval-body.png)
6. **Hayır ise, hiçbir şey yapmayın**, **öğe reddedildiğinde** e-posta iletisinin gövdesini belirt dışında bu yordamda 1-5 arasındaki adımları yineleyin.
   
    ![Reddetme e-postası gövdesi](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Reddedilen dosyaları sil
1. Reddetme e-postası alanları altında **Eylem Ekle**' ye tıklayın veya dokunun.
   
    ![Silme eylemi Ekle](./media/common-data-model-approve/add-delete-action.png)
2. **Daha fazla eylem ara**' yı Içeren kutuya **Dropbox**yazın veya yapıştırın ve ardından **Dropbox-dosyayı Sil**' e tıklayın veya dokunun.
   
    ![Dropbox 'tan Dosya Sil](./media/common-data-model-approve/dropbox-delete-file.png)
3. **Dosya**' nın altında, kutuya tıklayın veya dokunun ve ardından alana eklemek için **dosya tanımlayıcı** belirteci parametresine tıklayın veya dokunun.
   
    ![Silinecek dosyayı tanımla](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Akışı kaydetme
1. Ekranın üst kısmında oluşturmakta olduğunuz akış için bir ad yazın veya yapıştırın ve ardından **akış oluştur**' a tıklayın veya dokunun.
   
    ![akışı Kaydet](./media/common-data-model-approve/save-flow.png)
2. **Kapat** ' a ve ardından **bitti**' ye tıklayın veya dokunun.
3. Dropbox 'ta, belirttiğiniz klasöre en az iki dosya ekleyin: bir tane, onayı test etmek ve diğeri de ret etmek için.

## <a name="build-the-app"></a>Uygulamayı oluşturma
1. [PowerApps.com](https://web.powerapps.com)' da oturum açın ve ardından sol gezinti çubuğunun alt kısmında bulunan **Yeni uygulama** ' ya tıklayın veya dokunun.
   
    ![Tarayıcıda uygulama oluşturma](./media/common-data-model-approve/new-app-button.png)
2. Görüntülenen iletişim kutusunda, Windows için PowerApps Studio veya Web için PowerApps Studio açma seçeneğine tıklayın veya dokunun.
3. Windows için PowerApps Studio açtıysanız sol gezinti çubuğunda **Yeni** ' ye tıklayın veya dokunun.
4. **Verilerden uygulama oluşturma**altında **Common Data Service** kutucuğunda **Telefon düzeni** ' ne tıklayın veya dokunun.
   
    ![Uygulama oluştur](./media/common-data-model-approve/afd-cdm.png)
5. **Arama** kutusuna **Gözden geçirme**yazın veya yapıştırın.
   
    ![Varlık arama](./media/common-data-model-approve/search-entities.png)
6. **Varlık seçin**altında **Dropbox dosyalarını incele**' ye tıklayın veya dokunun.
   
    ![Bir varlık seçin](./media/common-data-model-approve/choose-entity.png)
7. Sağ alt köşenin yakınında, **Bağlan**' a tıklayın veya dokunun.
   
    ![Bağlan düğmesi](./media/common-data-model-approve/connect-button.png)
8. Giriş turu açılış ekranı görüntülenirse PowerApps 'i (veya **Atla**' ya tıklayın veya dokunun) öğrenmeye yönelik tura katılın.
   
    ![Tanıtım turu](./media/common-data-model-approve/quick-tour.png)
   
    Turu daha sonra, sol üst köşedeki soru işareti simgesine tıklayarak veya dokunarak ve ardından **tanıtım turuna katılarak**veya dokunarak istediğiniz zaman alabilirsiniz.
9. seçim Ekranın alt kısmındaki kaydırıcıyı sürükleyerek uygulamanın daha kolay görünmesi için kaydırıcıyı sürükleyin.
   
    ![Yakınlaştırma denetimi](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Uygulamayı özelleştirme
1. Sağ gezinti çubuğunda bir başlık ve açıklama içeren düzene tıklayın veya dokunun.
   
    ![Bağlan düğmesi](./media/common-data-model-approve/choose-layout.png)
2. **BrowseScreen**üzerinde, daha büyük metin kutusu denetimini seçmek için arama çubuğunun hemen altına tıklayın veya dokunun.
   
    ![Üst bilgi Seç](./media/common-data-model-approve/select-header.png)
3. Sağ bölmede, aşağı okuna tıklayarak veya dokunarak aşağı açılan listeyi açın.
   
    ![Açılan menüyü aç](./media/common-data-model-approve/open-dropdown.png)
4. Alt listede, **başlık** ' a tıklayın veya dokunun. bu nedenle, eklenen dosyaların dosya adını gösterin.
   
    ![Başlık verilerini ayarlama](./media/common-data-model-approve/set-heading.png)
5. Sağ bölmede, üstteki listeyi açın ve ardından **durum** ' a tıklayarak veya dokunarak her bir dosyanın durumunu görüntüleyin.
   
    ![Gövde verilerini ayarlama](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Genel çözümü test etme
1. PowerApps 'te, sol üst köşedeki Oynat düğmesine tıklayarak veya dokunarak Önizleme modunu açın.
   
    ![Önizleme modunu aç](./media/common-data-model-approve/open-preview.png)
2. Listedeki ilk dosya için oka tıklayın veya dokunun ve bu dosya hakkındaki ayrıntıları gösterin.
   
    ![Ayrıntılar ekranını aç](./media/common-data-model-approve/open-details.png)
3. Dosya hakkındaki ayrıntıları değiştirmek için sağ üst köşedeki kalem simgesine tıklayın veya dokunun.
   
    ![Düzenleme ekranını aç](./media/common-data-model-approve/edit-record.png)
4. **Durum** kutusuna **Onaylandı**yazın veya yapıştırın.
   
    ![Bir dosyayı onaylama](./media/common-data-model-approve/change-status.png)
5. Değişikliklerinizi kaydetmek ve Ayrıntılar ekranına geri dönmek için sağ üst köşedeki onay işareti simgesine tıklayın veya dokunun.
   
    ![Değişiklikleri Kaydet](./media/common-data-model-approve/save-record.png)
   
    Birkaç dakika içinde, dosyanın onaylanmış olduğunu belirten bir e-posta alacaksınız.
6. Sağ üst köşedeki geri düğmesine tıklayarak veya dokunarak gezinme ekranına geri dönün.
   
    ![Tarama ekranına dön](./media/common-data-model-approve/back-arrow.png)
7. Listedeki diğer dosya için oka tıklayın veya dokunun ve bu dosya hakkındaki ayrıntıları gösterin.
   
    ![Ayrıntılar ekranını aç](./media/common-data-model-approve/open-details.png)
8. Dosya hakkındaki ayrıntıları değiştirmek için sağ üst köşedeki kalem simgesine tıklayın veya dokunun.
   
    ![Düzenleme ekranını aç](./media/common-data-model-approve/edit-record.png)
9. **Durum** kutusunda, **reddedildi** (veya **onaylanan veya onay** **dahil olmak** **üzere) ' i yazın veya yapıştırın**.
   
    ![Dosyayı Reddet](./media/common-data-model-approve/reject-file.png)
10. Değişikliklerinizi kaydetmek ve Ayrıntılar ekranına geri dönmek için sağ üst köşedeki onay işareti simgesine tıklayın veya dokunun.
    
     ![Değişiklikleri Kaydet](./media/common-data-model-approve/save-record.png)
    
     Birkaç dakika içinde, dosyanın reddedildiğini belirten bir e-posta alacaksınız ve dosya Dropbox 'tan silinir.

