---
title: Klasik Common Data Service iş akışlarını Microsoft Flow ile Değiştir | Microsoft Docs
description: Klasik bir iş akışı yerine Flow kullanmak için Microsoft Flow özellikleri ve önerilen desenleri açıklar.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 08/27/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c824f726df991aba9aa1290eb117cf87113041a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548517"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Klasik Common Data Service iş akışlarını akışlarla değiştirme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu konu, Microsoft Flow yeteneklerini klasik iş akışıyla karşılaştırır.

Microsoft Flow, klasik iş akışı modeli üzerinde önemli avantajlar sağlar; Klasik iş akışı yerine işlemlerinizi otomatikleştirmek için Microsoft Flow kullanmayı göz önünde bulundurmanız gerekir. 

Yeni otomasyon süreçlerini derlemek için klasik Common Data Service iş akışları yerine akışlar oluşturun. Ayrıca, var olan klasik iş akışı işlemlerinizi gözden geçirmeniz ve akışlar ile değiştirmeyi göz önünde bulundurmanız gerekir.

## <a name="feature-capability-comparison"></a>Özellik yeteneği karşılaştırması

Bu tablo, Microsoft Flow ile klasik iş akışları özellikleri arasında bir karşılaştırma özetler. 

*Microsoft Flow için sürekli olarak yeni yetenekler ekliyoruz, böylece klasik iş akışı özelliğinden daha iyi ve hatta daha iyidir. Microsoft Flow kazanç özellikleri olarak bu tablodaki bilgileri güncelleştireceğiz; sıklıkla tekrar kontrol edin! Klasik iş akışını Flow ile değiştirmenizi sağlayacak yaklaşan akış özellikleri hakkında daha fazla bilgi için, Nisan 2019 sürüm notlarındaki [Microsoft Flow yenilikler ve planlandı](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features) bölümüne bakın!*

<table>
<tr>
<th colspan="2">Yapma</th>
<th>Microsoft Flow</th>
<th>Klasik Iş akışı</th>
</tr>
<tr>
<td rowspan="5">Oluşturmanın</td>
<td>Koşullu dallanma</td>
<td>Yes</td>
<td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Döngüye
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Alanlarda bekleme koşulları
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Paralel dal
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Dış sistemlere kullanıma hazır bağlayıcılar (dış hizmetlerde tetikleyici ve işlemler gerçekleştirme)
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Birleştirme
                    
                </td>
                <td>
                    
   Dinamik içerik
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Olay verilerinin ön görüntüsüne erişim
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Alt iş akışlarını çalıştır
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Common Data Service eylemlerini çalıştır (özel dahil)
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Özel iş akışı etkinliklerini Çalıştır
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   İşlem içinde çalıştırılacak adımları gruplandırma
                    
                </td>
                <td>
                    
   Evet (değişiklik kümeleri)
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Onay iş akışları
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Yürütme
                    
                </td>
                <td>
                    
   Alan değişikliklerinde Tetikle
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Alan değerlerine koşullu tetikleme (örneğin, bir tarih alanında belirli bir tarih)
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Birden çok Common Data Service varlık olayına tetikleme
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   İsteğe bağlı olarak çalıştır
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Farklı Çalıştır kapsamları    <br/>
   (örneğin, kuruluş, iş birimi, Kullanıcı)
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Bir zamanlamaya göre Çalıştır
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Zaman uyumlu Çalıştır (gerçek zamanlı)
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Geçmişi
                    
                </td>
                <td>
                    
   Girdilerini
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Analizi Çalıştır
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   Yazma ve taşınabilirlik
                    
                </td>
                <td>
                    
   Çözüm desteği
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Modern tasarımcı
                    
                </td>
                <td>
                    
   Yes
                    
                </td>
                <td>
                    
   eşleşen
                    
                </td>
            </tr>
            <tr>
<td>AI destekli yazma</td>
<td>Yes</td>
<td>eşleşen</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>Örnek senaryo: iş akışını bir akışla değiştirme

Müşteri için bir teklif yerleştirdiğiniz ve şimdi, teklifi müşteriye göndermeden önce yönetim takımınızdan onay istemeniz gereken bir satış senaryosunu düşünün. Klasik iş akışlarıyla bu, bu kadar kolay bir işlemdir ve bunun çoğu çözümü, bir geliştiricinin teklif satırı öğelerini almak için özel iş akışı etkinlikleri yazmasını gerektirir.

Akışlar sayesinde, daha sonra senaryoyu desteklemeye yönelik bazı Microsoft Flow yeteneklerini ele alan izlenecek yolda gösterildiği gibi daha kolay bir şekilde oluşturabilirsiniz. Buna şunlar dahildir:

-   İsteğe bağlı olarak çalışan bir akış oluşturma

-   Common Data Service varlıkla ilgili kayıtların listesini alma

-   Kayıt listesi üzerinde döngü

-   Onay istekleri gönderiliyor

Satış kişisinin istek üzerine onay isteğini tetiklemesine izin vermek için:

1. [Microsoft Flow](https://flow.microsoft.com/) oturum açın ve çözümde bir akış oluşturun. Daha fazla bilgi: [bir çözümde akış oluşturma](create-flow-solution.md). 

1. Tetikleyiciler listesinden **Common Data Service (geçerli ortam): bir kayıt seçildiğinde** ve varlık olarak **teklifler** ' i seçin. Bu tetikleyici bir kayıt veya kayıt listesi üzerinde isteğe bağlı olarak bir akışın çalıştırılmasına izin verir.

1. Tetikleyici yapılandırıldığında, akışımızda çalıştırılacak eylemler ekleyin. Bu, onaylayan öğe ve değerleri belirlemek için ihtiyaç duydukları özet ayrıntılarını onaylayan olarak sağlayacaktır. **Common Data Service (geçerli ortam) – kayıtları Listele** eylemini ekleyerek başlayın. Bir tekliften ayrı satır öğeleri almak istiyoruz, varlığı **teklif satırları**olarak ayarlayın. Yalnızca akışın tetiklendiği teklife ait olan teklif satırı öğelerini listeleyebilmemiz için bir OData stil filtresi ölçütü belirteceğiz. **Filtre sorgusu** alanına *\_quoteid_value EQ* yazın ve görüntülenen dinamik değerler listesinden *quote* ' yı seçin.

    ![Akışınızı tanımlama](media/define-flow-1.png "Akışınızı tanımlama")

1. Onay için teklif satırı öğelerini özetlemek istiyoruz, **değişken Başlat** eylemini ekleyin. **Ad** alanını *quote satırı Özeti* ve **türü** dize olarak ayarlayın (açılan kutudan) ve **değer** alanını boş bırakın.

1. **Dize değişkenine Ekle** eylemini ekleyin ve daha önce oluşturduğumuz *teklif satırı Özet* değişkenini seçin. **Değer** alanında, dinamik değerler listesinden *Miktar, ad, birim başına fiyat, genişletilmiş miktar ve el ile miktar* ' ı seçin. Microsoft Flow Tasarımcısı, bu değerlerin bir teklif satırı öğeleri listesinden olduğunu belirler ve her bir satır öğesinden gelen bilgilerin bu özete eklenmesini sağlamak için bu eylemi her döngüde bir **uygulamaya** ekler.

    ![Akışınızı tanımlama](media/define-flow-2.png "Akışınızı tanımlama")

1. Oluşturduğumuz teklif Özeti hakkında onay istemek için **onay ekleyin – başlangıç ve onay eylemi bekleme** . Bir onay türü seçin (örneğin, onayla/reddet – öncelikle yanıt vermek üzere), onay isteğine bir **başlık** verin (örneğin, onaylamanız Istenen teklifin adı, dinamik değerler listesinden çekilir), **atanan** alanında teklifi gözden geçirmesi ve onaylaması gereken kişi. Ayrıntılar alanında, *tırnak satırı Özet* değişkenini ve dinamik değer seçiciyle ilgili olabilecek diğer bilgileri (örneğin, toplam tutar) ekleyin.

1. Onay kabul edildiğinde veya reddedildiğinde ne olacağını belirlemek için **koşul** eylemini ekleyin. Koşuldaki ilk alandan dinamik değerler listesinden *sonuç* ' i seçin, ikinci alandaki açılan listeden öğesini *içerir* ve koşulun üçüncü alanına *kabul et* ' i girin. Son olarak, onay sonucuna göre eylemler ekleyin (örneğin, bir bildirim e-postası gönderin).

    ![Akışınızı tanımlama](media/define-flow-3.png "Akışınızı tanımlama")

Artık onay yapısına, onaylayanın sonraki adımlarda bir karar vermek için gereken tüm bilgilere sahip olması gerekir. Onay istemek için isteğe bağlı tam akış akışı aşağıda verilmiştir:

![Onay akışı yapısı](media/approval-flow-structure.png "Onay akışı yapısı")

Bu akışı teklifinize göre çalıştırdığınızda, bu teklif için teklif satırı öğelerini özetler ve onaylayanın Microsoft Flow veya aldıkları e-postalardan yanıt verebildiği bir onay isteği gönderir. Aşağıda bir ekran örneği verilmiştir:

![Flow eyleminde](media/flow-in-action.png "Flow eyleminde")

## <a name="recommended-patterns"></a>Önerilen desenler


-   **Karmaşık Else-If koşullu Logic ile iş akışları**  
    
    Koşulları kullanmak yerine, bunun yerine [Switch eylemini](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement) kullanmanızı öneririz.

-   **Eklentiden/koddan çalışan iş akışları**  
    
    Tetikleyici ile başlamak için akışın yeniden tasarlanmasını öneririz.

    -   Akışları, içindeki olaylara göre çalıştırmak için Common Data Service Tetikleyicileri kullanın.

    -   Dış bir hizmette bulunan olaylara göre akışları çalıştırmak için 260 'den fazla kullanıma hazır bağlayıcı üzerinden yararlanın.

    -   İhtiyaç duyduğunuz bir bağlayıcının kullanıma hazır olmadığından, kendi özel bağlayıcınızı kolayca oluşturarak [özel bağlayıcılar oluşturmayı öğrenin](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

    -   Son olarak, Common Data Service Bağlayıcısı kullanarak akışınızı tetikleyebileceğiniz veya hazır olmayan bağlayıcılardan biri olan senaryolar varsa veya özel bir bağlayıcı oluşturursanız, akışı çağırmak için [BIR http isteği alındığında tetiklenir](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger)

-   **Yinelemeli çalışan iş akışları**  
    
    Bunun yerine akışlarda [Do-Until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) veya [her döngü için Uygula](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop) ' yı kullanın

-   **Kayıt listesi gerektiren iş akışları**  
    
    **Kayıtları Listele** eylemini kullanın. Bu eylemi kullanırken, geri almak istediğiniz kayıt sayısını en aza indirerek eylemi iyileştirmek için OData söz dizimini kullanarak kayıt filtreleme ölçütlerini tanımlayın.

-   **Bir zamanlamaya göre çalışabilecek iş akışları**  
    
    Düzenli aralıklarla iş mantığını çalıştırmak için **yinelenme** tetikleyicisini kullanın.

-   **Etkinliklerin tek bir işlemde yürütüldüğünü sağlamak için çalıştırılan iş akışları yönetiliyor**  
    
    [İçindeki tüm eylemlerin tümünün başarılı veya bir grup olarak başarısız olduğu tek bir atomik birim olarak gerçekleştirildiğinden emin olmak için [değişiklik kümesi eylemini](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) kullanın. Değişiklik kümesindeki eylemlerden herhangi biri başarısız olursa, tamamlanan işlemler tarafından yapılan değişiklikler geri alınır.

-   **İş akışı çalıştırmalarını hatalara karşı izle**  
    
    Microsoft Flow ' de, önceki eylem başarısız olduğunda çalışacak şekilde yapılandırmak için bir eylemde **Çalıştır ayarını** kullanın. Örneğin, **bir kayıt güncelleştirme** eyleminin başarısız olduğu veya zaman aşımına uğradığında Microsoft Flow bir mobil bildirim gönderin.

## <a name="faqs"></a>Sık


-   **Dynamics 365 lisansına sahibim. Microsoft Flow kullanabilir miyim?**

    Her Dynamics 365 kullanıcısına Microsoft Flow kullanma hakkı vardır. Lisanslama bilgilerinizi gözden geçirin: <https://flow.microsoft.com/pricing/>

-   **Akışlarım ne sıklıkla tetiklenebilir?**

    -   Dynamics 365 (veya Common Data Service) akışları, Web kancalarını kullandıkları için tetikleyiciden sonra neredeyse gerçek zamanlı çalışır (yoklama gerekmez)

    -   Doğrudan API erişimi sayesinde, sistemde tam olarak belgelendiği gibi kısıtlar/sınırlar vardır: <https://docs.microsoft.com/flow/limits-and-config>

    -   Özellikle, akış başına 5 dakika başına 100.000 eylem sınırı vardır ve bir akışta tek bir döngü aynı anda 100.000 öğeden fazlasını işleyemez

    -   5 dakika başına en fazla 6 GB aktarım hızı

-   **Tek bir akış ne kadar süreyle çalıştırılabilir?**  
    
    30 gün sonra tek bir akış çalıştırması zaman aşımına uğrar.

-   **Akışlarımı ortamlar arasında taşımak Nasıl yaparım? mı?**  
    
    Yalnızca klasik iş akışlarıyla olduğu gibi, bir işlem için tam uygulama yaşam döngüsünü desteklemek üzere çözümlerde akışlar oluşturabilirsiniz.

-   **Microsoft Flow bağımlılıklar Common Data Service izleniyor mu?**  
    
    Çözümdeki diğer bileşenlere benzer şekilde, çözümlerdeki akışlar için tüm bağımlılıklar Common Data Service izlenir.

-   **Zaman uyumlu iş akışları ne?** 
 
    Hedefin veya iş akışının bölümlerinin bir akış kullanılarak oluşturulup oluşturulmayacağını belirlemek için zaman uyumlu iş akışlarının gereksinimini yeniden değerlendirmelisiniz. Özellikle, zaman uyumlu iş akışlarının, genel Son Kullanıcı düşük performans deneyimine yönelik önemli bir katkı olduğunu inceleyeceğiz. Birçok kullanım için, bu eylemleri zaman uyumsuz olarak ayırmak tercih edilebilir, ancak Microsoft Flow işlemin tamamlanmasını sağlamaya devam ederken kullanıcının etkinlikleriyle devam edebilmesi için bu eylemleri zaman uyumsuz olarak bölmeniz tercih edilir.

-   **Microsoft Flow kullanarak verilerim bölge içinde kalır (yani, Dynamics 365 veya Common Data Service ortamım ile aynı bölge)?**  
    
    Evet, Microsoft Flow her zaman Common Data Service aynı bölgeyi kullanır.

-   **Ara sunucu/güvenlik duvarı değişiklikleri yapmam gerekiyor mu?**  
    
    Herhangi bir proxy/güvenlik duvarı değişikliği yapmanız gerekip gerekmediğini öğrenmek için [IP adresi yapılandırma başvurusuna](limits-and-config.md#ip-address-configuration) bakın.
