---
title: PowerApps'te iş süreci akışı oluşturma | MicrosoftDocs
description: İş süreci akışı oluşturmayı öğrenin
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: 258fedabea816b9a20a8f768632e797dec576365
ms.sourcegitcommit: d3243c9f82c5e058919c5cb85d36d45f1f034411
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2018
ms.locfileid: "43774237"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Öğretici: Süreçleri standartlaştırmak için bir iş süreci akışı oluşturma

Bu öğreticide PowerApps ile iş süreci akışı oluşturma adımları gösterilmektedir. İş süreci akışlarını kullanma nedenleri hakkında daha fazla bilgi edinmek için bkz. [İş süreci akışlarına genel bakış](business-process-flows-overview.md). Mobil görev akışı oluşturma hakkında daha fazla bilgi için bkz. [Mobil görev akışı oluşturma](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Kullanıcı bir iş süreci akışı başlattığında sürecin aşamaları ve adımları formun üst kısmında bir süreç çubuğu şeklinde görüntülenir:  
  
 ![İş süreci aşamaları](media/business-process-stages.png "İş süreci aşamaları")  
  
 > [!TIP]
 >  Oluşturduğunuz iş süreci akışı örneği üzerinde oluşturma, okuma, güncelleştirme veya silme iznine sahip olacak kişileri denetleyebilirsiniz. Örneğin hizmetle ilgili süreçler için müşteri hizmetleri temsilcilerine iş süreci akışı örneğini değiştirme izni verebilir ancak müşterileri için satış sonrası etkinlikleri izlemesi gereken satış temsilcilerine salt okunur erişim verebilirsiniz. Oluşturduğunuz bir iş süreci akışı tanımında güvenlik ayarlarını etkinleştirmek için eylem çubuğundan **Güvenlik Rollerini Etkinleştir**'i seçin.  
  
<a name="BKMK_Createbusinessprocessflows"></a>   
## <a name="create-a-business-process-flow"></a>İş süreci akışı oluşturma  
  
1. [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)'ni açın.
  
2. Soldaki gezinti bölmesinde **İşlemler**'i seçin. 
  
3.  **Eylemler** araç çubuğunda **Yeni**'yi seçin.  
  
4.  **İşlem Oluştur** iletişim kutusunda gerekli alanları doldurun:  
  
    -   İşlem adı girin. İşlem adının benzersiz olması şart değildir ancak işlem seçecek kişilere kolaylık sağlaması için anlaşılır olmalıdır. Bunu daha sonra değiştirebilirsiniz.  
  
    -   **Kategori** listesinde **İş Süreci Akışı**'nı seçin.  
  
         İşlemi oluşturduktan sonra kategoriyi değiştiremezsiniz.  
  
    -   **Varlık** listesinde işlem için temel almak istediğiniz varlığı seçin.  
  
         Seçtiğiniz varlık, süreç akışının ilk aşamasına eklenebilecek adımlar için kullanılabilecek alanları etkiler. İstediğiniz varlığı bulamıyorsanız varlık tanımında İş süreci akışları (alanlar oluşturulacak) seçeneğinin belirlenmiş olduğundan emin olun. İşlemi kaydettikten sonra bunu değiştiremezsiniz.  
  
5. **Tamam**’ı seçin.  
  
     Yeni işlem oluşturulur ve tek aşama oluşturulmuş şekilde iş süreci akışı tasarımcısı açılır.  
  
 ![Ana öğeleri gösteren iş süreci akış penceresi](media/business-process-flow-window-showing-main-elements.png "Ana öğeleri gösteren iş süreci akış penceresi")  
  
6. **Aşama ekleyin.** Kullanıcılarınız süreç içinde bir iş aşamasından diğerine ilerleyecekse:  
  
    1.  **Bileşenler** sekmesinden bir **Aşama** bileşenini sürükleyip tasarımcıdaki + işaretlerinden birinin üzerinde bırakın.  
  
        ![İş süreci aşaması sürükleme](media/drag-business-process-stage.png "İş süreci aşaması sürükleme")  
  
    2.  Bir aşamanın özelliklerini ayarlamak için aşamayı seçin ve ekranın sağ tarafındaki **Özellikler** sekmesinde özellikleri ayarlayın:  
  
        -   Görünen ad girin.  
  
        -   İsterseniz aşama için bir kategori seçin.  Kategori (**Niteleme** veya **Geliştirme** gibi) süreç çubuğunda köşeli çift ayraç olarak görünür.  
  
            ![İş süreci çubuğundaki köşeli çift ayraç](media/business-process-bar-chevron.png "İş süreci çubuğundaki köşeli çift ayraç")  
  
        -   Özellikleri değiştirmeyi tamamladığınızda **Uygula** düğmesini seçin.  
  
7. **Aşamaya adım ekleyin.** Bir aşamadaki adımları görmek için aşamanın sağ alt köşesinden **Ayrıntılar**'ı seçin. Daha fazla adım eklemek için:  
  
    1.  **Bileşenler** sekmesinden **Adım** bileşenini aşamaya sürükleyin.  
  
        ![İş sürecindeki bir aşamaya adım ekleme](media/add-step-stage-business-process.png "İş sürecindeki bir aşamaya adım ekleme")  
  
    2.  Adımı seçin ve ardından **Özellikler** sekmesinden özellikleri ayarlayın:  
  
        1.  Adım için görünen ad girin.  
  
        2.  Kullanıcıların bir adımı tamamlamak için veri girmesini istiyorsanız açılan listeden uygun alanı seçin.  
  
        3.  Kullanıcıların sürecin bir sonraki aşamasına geçebilmek için alanı doldurmalarını zorunlu kılmak istiyorsanız **Gerekli**'yi seçin.  
  
        4.  İşlemi tamamladığınızda **Uygula**'yı seçin.  
  
8. **Sürece dal (koşul) ekleyin.** Dallanma koşulu eklemek için:  
  
    1.  **Bileşenler** sekmesinden **Koşul** bileşenini sürükleyip iki aşama arasındaki + işaretine bırakın.  
  
        ![İş süreci akışına koşul ekleme](media/add-condition-business-process-flow.png "İş süreci akışına koşul ekleme")  
  
    2.  Koşulu seçin ve ardından **Özellikler** sekmesinden özellikleri ayarlayın. Dallanma özellikleri hakkında daha fazla bilgi için bkz. [Dallanma ile iş süreci akışlarını geliştirme](enhance-business-process-flows-branching.md). Koşulun özelliklerini ayarlamayı tamamladığınızda **Uygula**'yı seçin.  
  
9. **İş akışı ekleyin.** Bir iş akışını çağırmak için:  
  
    1.  **Bileşenler** sekmesinden bir **İş akışı** bileşenini tasarımcıdaki aşamalardan birine veya **Genel İş Akışı** öğesine sürükleyin.   Hangisine ekleyeceğiniz aşağıdakilere bağlıdır:  
  
       - Aşamanın girişinde veya çıkışında iş akışını tetiklemek için **bir aşamaya sürükleyin**. İş akışı bileşeninin aşamayla aynı birincil varlığı temel alması gerekir.  
  
       - İş akışını süreç etkinleştirildiğinde veya arşivlendiğinde (durum **Tamamlandı** veya **Bırakıldı** olarak değiştiğinde) tetiklemek için **Genel İş Akışı öğesine sürükleyin**. İş akışı bileşeninin süreçle aynı birincil varlığı temel alması gerekir.  
  
    2.  İş akışını seçin ve ardından **Özellikler** sekmesinden özellikleri ayarlayın:  
  
       1.  Görünen ad girin.  
  
       2.  İş akışının tetikleneceği koşulu belirleyin.  
  
       3.  Aşama varlığıyla eşleşen var olan bir istek üzerine etkin iş akışı arayın veya **Yeni**'yi seçerek yeni bir iş akışı oluşturun.  
  
       4.  İşlemi tamamladığınızda **Uygula**'yı seçin.  
  
       İş akışları hakkında daha fazla bilgi için bkz. [İş akışı süreçleri](../common-data-service/workflow-processes.md).  
  
10. İş süreci akışını doğrulamak için eylem çubuğunda **Doğrula**'yı seçin.  
  
11. Üzerinde çalışmaya devam ederken süreci taslak olarak kaydetmek için eylem çubuğunda **Kaydet**'i seçin.  
  
    > [!IMPORTANT]
    >  Taslak halindeki süreçler kullanıcılar tarafından kullanılamaz.  
  
12. Süreci etkinleştirmek ve ekibinizin kullanımına açmak için eylem çubuğunda **Etkinleştir**'i seçin.  

13. İş süreci akışı örneği üzerinde oluşturma, okuma, güncelleştirme veya silme yetkisine sahip olacak kişileri denetlemek için tasarımcının komut çubuğunda **Güvenlik Rollerini Düzenle**'yi seçin. Örneğin hizmetle ilgili süreçler için müşteri hizmetleri temsilcilerine iş süreci akışı örneğini değiştirme izni verebilir ancak müşterileri için satış sonrası etkinlikleri izlemesi gereken satış temsilcilerine salt okunur erişim verebilirsiniz.

  **Güvenlik Rolleri** ekranında rol adlarına tıklayarak güvenlik rolü bilgi sayfasını açabilirsiniz. İş Süreci Akışları sekmesini seçin ve iş süreci akışında güvenlik rolüne uygun ayrıcalıkları atayın.

  > [!NOTE]
  > Sistem Yöneticisi ve Sistem Özelleştirici güvenlik rolleri varsayılan olarak yeni iş süreci akışlarına erişebilir.

   ![İş süreci akışına ayrıcalık atama](media/bpf-assign-privileges.png)

  Uygun radyo düğmelerini seçerek ayrıcalıkları belirtin ve Kaydet'e tıklayın. Ayrıcalıklar hakkında daha fazla bilgi için bkz. [İş süreci akışı ayrıcalıkları](business-process-flows-overview.md#BKMK_MultipleBPF).

  Ardından güvenlik rolünü kuruluşunuzdaki uygun kullanıcılara atamayı unutmayın.

> [!TIP] 
>  Aşağıda tasarımcı penceresinde görev akışınızın üzerinde çalışırken aklınızda bulundurmanız gereken bazı ipuçları verilmiştir:  
>   
> - İş süreci akışı penceresindeki tüm öğelerin anlık görüntüsünü almak için eylem çubuğundaki **Anlık görüntü**'yi seçin. Bu eylem süreci ekip arkadaşlarınızla paylaşıp yorumlarını almak istediğiniz gibi durumlarda kullanışlıdır.  
> - Sürecin farklı bölümlerine hızla ulaşmak için mini haritayı kullanın. Bu işlem özellikle ekrandan taşan karmaşık bir süreciniz olduğunda kullanışlıdır.  
> - İş sürecine açıklama eklemek için iş süreci akışı penceresinin sol köşesindeki süreç adının altında bulunan **Ayrıntılar**'ı seçin. En fazla 2000 karakter uzunluğunda yazabilirsiniz.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>İş süreci akışını düzenleme  
 İş süreci akışlarını düzenlemek için Çözüm Gezgini'ni açın, **İşlemler**'i seçin ve açılan süreç listesinden düzenlemek istediğiniz **İş Süreci Akışını** belirleyin.  
  
 Süreç listesinden düzenlemek istediğiniz iş süreci akışının adını seçtiğinizde istediğiniz güncelleştirmeleri yapabileceğiniz tasarımcı görünümü açılır. Yeniden adlandırmak, açıklama eklemek veya ek bilgileri görüntülemek için sürecin altındaki **Ayrıntılar** bölümünü genişletin.  
  
 ![İş süreci akışının genişletilmiş ayrıntılar bölümü](media/business-process-flow-details.png "İş süreci akışının genişletilmiş ayrıntılar bölümü")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>İş süreci akışları hakkında bilmeniz gereken diğer noktalar
 **Aşamaları Düzenleme**  
İş süreci akışlarında en fazla 30 aşama bulunabilir.    
  
Bir aşamada şu özellikleri ekleyebilir veya değiştirebilirsiniz:  
  
- **Aşama Adı**  
  
- **Varlık**. Birinci aşama hariç tüm aşamaların varlığını değiştirebilirsiniz.  
  
- **Aşama Kategorisi**. Kategoriler, aşamaları eylem türüne göre gruplamanızı sağlar. Kayıtları bulundukları aşamalara göre gruplayacak olan raporlar için kullanışlıdır. Aşama kategorisi seçenekleri, Aşama Kategorisi genel seçenek kümesinden alınır. İsterseniz bu genel seçenek kümesine ek seçenekler ekleyebilir ve var olan seçeneklerin etiketlerini değiştirebilirsiniz. Ayrıca isterseniz bu seçenekleri silebilirsiniz ancak var olan seçenekleri korumanız önerilir. Sildiğiniz seçeneği aynı şekilde ekleme seçeneğiniz olmayacaktır. Kullanılmasını istemediğiniz seçeneklerin etiketini "Kullanmayın" olarak değiştirebilirsiniz.  
  
- **İlişki**. Sürecin bir önceki aşaması farklı bir varlığı temel alıyorsa ilişki girebilirsiniz. Tanımlamakta olan aşama için **İlişkileri seç**'i belirleyerek iki aşama arasında geçiş yapılırken kullanılacak ilişkiyi tanımlayabilirsiniz. Sağladığı şu avantajlar nedeniyle ilişkiyi seçmeniz önerilir:  
  
    -   İlişkiler genellikle tanımlı olan ve verileri otomatik olarak kayıtlar arasında aktararak veri girişini en aza indiren öznitelik eşlemelerine sahiptir.  
  
    -   Bir kayıt için süreç çubuğunda **Sonraki Aşama**'yı seçtiğinizde ilişkiyi kullanan tüm kayıtlar iş akışında listelenir ve süreçte kayıtların yeniden kullanılmasını sağlar. Ayrıca iş akışlarını kullanarak kayıtların otomatik olarak oluşturulmasını ve böylece kullanıcının yeni bir tane oluşturmak yerine bunu seçerek süreci kolaylaştırmasını sağlayabilirsiniz.  
  
**Adımları Düzenleme**  
 Her aşamada en fazla 30 adım olabilir.    
  
**Dal ekleme**  
Bir aşamaya dal ekleme hakkında bilgi edinmek için bkz. [Dallanma ile iş süreci akışlarını geliştirme](enhance-business-process-flows-branching.md).  
  
Bir iş süreci akışını kullanıcıların erişimine açmak için süreç akışını sıralamanız, güvenlik rollerini etkinleştirmeniz ve akışı etkin hale getirmeniz gerekir.  
  
**Süreç Akış Sırasını Ayarlama**  
 Bir varlık (kayıt türü) için birden fazla iş süreci akışınız varsa yeni kayıtlara otomatik olarak atanacak süreci belirlemeniz gerekir. Komut çubuğunda **Süreç Akışını Sırala**'yı seçin. Yeni veya bir süreç akışıyla ilişkilendirilmemiş olan kayıtlar için kullanıcının erişimi olan ilk iş süreci akışı kullanılacaktır.  
  
**Güvenlik Rollerini Etkinleştirme**  
Kullanıcılar, kendilerine atanmış olan güvenlik rolü için iş süreci akışında tanımlanmış olan ayrıcalığa göre iş süreci akışına erişim sağlar. 

Varsayılan olarak yalnızca **Sistem Yöneticisi** ve **Sistem Özelleştirici** güvenlik rolleri yeni bir iş süreci akışını görüntüleyebilir. 

Bir iş süreci akışındaki ayrıcalıkları belirlemek için düzenlenecek iş süreci akışını açın ve iş süreci akışı tasarımcısının komut çubuğunda **Güvenlik Rollerini Düzenle**'yi seçin. Bu konunun üst kısımlarındaki [İş süreci akışı oluşturma](#create-a-business-process-flow) bölümünün 13. adımına bakın.
  
**Etkinleştirme**  
İş sürecinin kullanılabilmesi için etkinleştirmeniz gerekir. Komut çubuğunda **Etkinleştir**'i seçin. Etkinleştirme onaylandıktan sonra iş süreci akışı kullanıma hazır olur. İş süreci akışında hatalar varsa bu hataları düzeltene kadar etkinleştirme gerçekleştiremezsiniz.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>İş süreci akışına isteğe bağlı eylem ekleme
Dynamics 365 (çevrimiçi) sürüm 9.0 güncelleştirmesi ile yeni bir iş süreci akışı özelliği eklenmiştir: Eylem Adımları ile iş süreci akışı otomasyonu. Bir iş süreci akışına bir eylemi veya iş akışını tetikleyecek bir düğme ekleyebilirsiniz.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Eylem Adımı kullanarak isteğe bağlı iş akışları veya eylemler ekleme
Contoso kuruluşundaki fırsat değerlendirme sürecinin bir parçası olarak tüm fırsatların belirlenen bir gözden geçiren tarafından incelenmesi gerektiğini düşünün. Contoso kuruluşu bu nedenle şöyle bir eylem oluşturmuştur: 

- Fırsatları gözden geçiren kişiye atanmış olan bir görev kaydı oluşturur. 
- Fırsat konusuna "Gözden geçirme için hazır" ifadesini ekler. 

Ayrıca Contoso'nun bu eylemleri istek üzerine çalıştırabilmesi gerekmektedir. Bu görevleri fırsat değerlendirme süreciyle tümleştirmek için eylemlerin fırsat iş süreci akışında görünmesi gerekir. Bu işlevi etkinleştirmek için **İş Süreci Akışı Olarak eylem adımını seçin**.
![İş süreci akışı olarak çalıştırılabilir.](media/action-available-to-run.png)

Ardından Eylem Adımı, Contoso'nun fırsat iş süreci akışına eklenir. Sonrasında süreç akışı doğrulanır ve güncelleştirilir.

![Eylem İş Süreci Akışına eklenmiştir.](media/add-action-to-bpf.png)

Artık Contoso’nun satış ekibinin üyeleri eylemi **Fırsat Değerlendirme** iş süreci adımından **Yürüt**'ü seçerek isteğe bağlı olarak başlatabilir.

![Eylemi yürütün.](media/action-execute.png)

> [!IMPORTANT]
> - Bir eylemi veya iş akışını isteğe bağlı olarak yürütebilmek için iş süreci akışında bir Eylem Adımı bulunması gerekir. Eylem Adımı bir iş akışını çalıştırıyorsa bu iş akışının istek üzerine çalışacak şekilde yapılandırılması gerekir.
> - Eylem veya iş akışı ile ilişkilendirilmiş olan varlığın iş süreci akışı ile ilişkilendirilmiş olan varlıkla aynı olması gerekir.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Bir iş akış sürecinde Eylem Adımları kullanılmasıyla ilgili sınırlamalar

- Giriş veya çıkış parametreleri Entity, EntityCollection veya OptionSet (Picklist) türünde olduğunda eylemler, Eylem Adımları olarak kullanılamaz. Birden fazla EntityReference çıkış parametresine veya herhangi bir sayıda EntityReference giriş parametresine sahip olan eylemler, Eylem Adımları olarak kullanılamaz. Birincil varlıkla (genel eylem) ilişkilendirilmemiş olan eylemler, Eylem Adımları olarak kullanılamaz.

  
## <a name="next-steps"></a>Sonraki adımlar  
 [İş süreci akışlarına genel bakış](business-process-flows-overview.md) </br>   
 [Dallanma ile iş süreci akışlarını geliştirme](enhance-business-process-flows-branching.md)

