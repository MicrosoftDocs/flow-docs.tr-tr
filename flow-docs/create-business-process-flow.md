---
title: PowerApps 'te iş süreci akışı oluşturma | MicrosoftDocs
description: İş süreci akışı oluşturmayı öğrenin
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3bd154935e06031b031432e10fa977f23e1a2c54
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546525"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Öğretici: işlemleri standartlaştırmak için bir iş süreci akışı oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu öğreticide PowerApps ile iş süreci akışını nasıl oluşturacağınız gösterilmektedir. İş süreci akışlarını neden kullandığınız hakkında daha fazla bilgi edinmek için bkz. [iş süreci akışlarına genel bakış](business-process-flows-overview.md). Mobil görev akışı oluşturma hakkında daha fazla bilgi için bkz. [mobil görev akışı oluşturma](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Bir Kullanıcı bir iş süreci akışı başlattığında, işlemin aşamaları ve adımları formun üst kısmındaki işlem çubuğunda görüntülenir:  
  
 ![Aşamalarla iş süreci](media/business-process-stages.png "Aşamalarla iş süreci")  
  
 > [!TIP]
 >  Bir iş süreci akış tanımı oluşturduktan sonra, iş süreci akışı örneğini kimin oluştur, okuyabildiğini, güncelleştirebildiğini veya silmesine yönelik denetim sağlayabilirsiniz. Örneğin, hizmetle ilgili işlemler için, iş süreci akış örneğini değiştirmek üzere müşteri hizmetleri temsilcilerine yönelik tam erişim sağlayabilirsiniz, ancak satış temsilcilerine ait, satış sonrası etkinliklerini izleyebilmek için bu örneğe salt okuma erişimi sağlayabilirsiniz. müşterinizin. Oluşturduğunuz bir iş süreci akış tanımının güvenliğini ayarlamak için, eylem çubuğunda **güvenlik rollerini etkinleştir** ' i seçin.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Kaynakları

İş süreci akışları oluşturmak için [Flow plan 2](https://preview.flow.microsoft.com/pricing/) ' ye ihtiyacınız vardır. Bazı Dynamics 365 lisans planları, Flow planı 2 ' dir.

## <a name="create-a-business-process-flow"></a>İş süreci akışı oluşturma  
  
1. [Çözüm Gezginini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)açın.
  
2. Sol gezinti bölmesinde, **süreçler**' ı seçin. 
  
3.  **Eylemler** araç çubuğunda **Yeni**' yi seçin.  
  
4.  **Işlem oluştur** iletişim kutusunda gerekli alanları doldurun:  
  
    -   İşlem adı girin. İşlemin adının benzersiz olması gerekmez, ancak bir işlem seçmesi gereken kişilerin anlamlı olması gerekir. Bunu daha sonra değiştirebilirsiniz.  
  
    -   **Kategori** listesinde **iş süreci akışı**' nı seçin.  
  
         İşlemi oluşturduktan sonra kategoriyi değiştiremezsiniz.  
  
    -   **Varlık** listesinde, işlemi dayandırmak istediğiniz varlığı seçin.  
  
         Seçtiğiniz varlık, işlem akışının ilk aşamasına eklenebilecek adımlar için kullanılabilir alanları etkiler. İstediğiniz varlığı bulamazsanız, varlığın varlık tanımında Iş süreci akışları (alanları oluşturulacak alanlar) seçeneğinin ayarlanmış olduğundan emin olun. İşlemi kaydettikten sonra bunu değiştiremezsiniz.  
  
5. **Tamam ' ı**seçin.  
  
     Yeni işlem oluşturulur ve iş süreci akış Tasarımcısı sizin için önceden oluşturulmuş tek bir aşama ile açılır.  
  
 ![Ana öğeleri gösteren iş süreci akışı penceresi](media/business-process-flow-window-showing-main-elements.png "Ana öğeleri gösteren iş süreci akışı penceresi")  
  
6. **Aşamalar ekleyin.** Kullanıcılarınız işlemdeki bir iş aşamasından diğerine ilerlemeleri durumunda:  
  
    1.  Bir **aşama** bileşenini **Bileşenler** sekmesinden sürükleyip tasarımcıda + işaretine bırakın.  
  
        ![Bir iş süreci aşamasını sürükleyin](media/drag-business-process-stage.png "Bir iş süreci aşamasını sürükleyin")  
  
    2.  Bir aşamanın özelliklerini ayarlamak için aşamayı seçin ve ardından ekranın sağ tarafındaki **Özellikler** sekmesinden özellikleri ayarlayın:  
  
        -   Bir görünen ad girin.  
  
        -   İsterseniz, aşama için bir kategori seçin.  Kategori ( **uygun bulma** veya **geliştirme**gibi), işlem çubuğunda bir köşeli çift ayraç olarak görünür.  
  
            ![İş süreci çubuğu köşeli ayracı](media/business-process-bar-chevron.png "İş süreci çubuğu köşeli ayracı")  
  
        -   Özellikleri değiştirme işiniz bittiğinde **Uygula** düğmesini seçin.  
  
7. **Bir aşamaya adımlar ekleyin.** Bir aşamadaki adımları görmek için, aşamanın sağ alt köşesindeki **Ayrıntılar** ' ı seçin. Daha fazla adım eklemek için:  
  
    1.  **Adım** bileşenini **Bileşenler** sekmesinden aşamasına sürükleyin.  
  
        ![İş işlemindeki bir aşamaya adım ekleme](media/add-step-stage-business-process.png "İş işlemindeki bir aşamaya adım ekleme")  
  
    2.  Adımı seçin ve ardından **Özellikler sekmesinden özellikleri** ayarlayın:  
  
        1.  Adım için bir görünen ad girin.  
  
        2.  Kullanıcıların bir adımı tamamlaması için veri girmesini isterseniz, açılan listeden ilgili alanı seçin.  
  
        3.  İşlemin bir sonraki aşamasına geçmeden önce adımı tamamlaması gereken kişilerin alanı doldurması gerekiyorsa, **gereklidir** ' ı seçin.  
  
        4.  İşiniz bittiğinde **Uygula** ' yı seçin.  
  
8. **İşleme bir dal (koşul) ekleyin.** Dallanma koşulu eklemek için:  
  
    1.  **Koşul** bileşenini **Bileşenler** sekmesinden iki aşama arasında bir + işaretine sürükleyin.  
  
        ![İş süreci akışına koşul ekleme](media/add-condition-business-process-flow.png "İş süreci akışına koşul ekleme")  
  
    2.  Koşulu seçin ve ardından **Özellikler** sekmesinden özellikleri ayarlayın. Dallanma özellikleri hakkında daha fazla bilgi için bkz. [Dalla iş süreci akışlarını geliştirme](enhance-business-process-flows-branching.md). Koşul için özellikleri ayarlamayı tamamladığınızda **Uygula**' yı seçin.  
  
9. **Bir iş akışı ekleyin.** Bir iş akışını çağırmak için:  
  
    1.  Bir **Iş akışı** bileşenini **Bileşenler** sekmesinden bir aşamaya veya tasarımcıdaki **genel iş akışı** öğesine sürükleyin.   Bunu eklediğiniz yer, aşağıdakilere bağlıdır:  
  
       - İş akışını girişte veya aşamada çıkmak istediğinizde **bir aşamaya sürükleyin** . İş akışı bileşeni, aşama ile aynı birincil varlığa dayalı olmalıdır.  
  
       - İşlem etkinleştirildiğinde iş akışını tetiklemek istediğinizde veya işlem arşivlendiğinde (durum **tamamlandı** veya **bırakıldı**olarak değiştiğinde) **bunu genel iş akışı öğesine sürükleyin** . İş akışı bileşeni işlemle aynı birincil varlığa dayalı olmalıdır.  
  
    2.  İş akışını seçin ve ardından **Özellikler sekmesinden özellikleri** ayarlayın:  
  
       1.  Bir görünen ad girin.  
  
       2.  İş akışının tetiklenmesi gereken zaman ' ı seçin.  
  
       3.  Aşama varlığıyla eşleşen mevcut bir isteğe bağlı etkin iş akışını arayın veya **Yeni**' i seçerek yeni bir iş akışı oluşturun.  
  
       4.  İşiniz bittiğinde **Uygula** ' yı seçin.  
  
       İş akışları hakkında daha fazla bilgi için bkz. [Iş akışı süreçler](../common-data-service/workflow-processes.md).  
  
10. İş süreci akışını doğrulamak için eylem çubuğunda **Doğrula** ' yı seçin.  
  
11. Üzerinde çalışmaya devam ederken işlemi taslak olarak kaydetmek için, eylem çubuğunda **Kaydet** ' i seçin.  
  
    > [!IMPORTANT]
    >  Bir işlem taslak olduğu sürece insanlar bunu kullanamaz.  
  
12. İşlemi etkinleştirmek ve ekibiniz için kullanılabilir hale getirmek için eylem çubuğunda **Etkinleştir** ' i seçin.  

13. İş süreci akışı örneğini kimin oluşturerişebileceğini, okuyabildiğini, güncelleştirebildiğini veya silmesine yönelik denetim sağlamak için, tasarımcının komut çubuğunda **güvenlik rollerini Düzenle** ' yi seçin. Örneğin, hizmetle ilgili işlemler için, iş süreci akış örneğini değiştirmek üzere müşteri hizmetleri temsilcilerine yönelik tam erişim sağlayabilirsiniz, ancak satış temsilcilerine ait, satış sonrası etkinliklerini izleyebilmek için bu örneğe salt okuma erişimi sağlayabilirsiniz. müşterinizin.

  **Güvenlik rolleri** ekranında, güvenlik rolü bilgileri sayfasını açmak için bir rolün adını seçin. Iş süreci akışları sekmesini seçin ve ardından bir güvenlik rolü için iş süreci akışına uygun ayrıcalıkları atayın.

  > [!NOTE]
  > Sistem Yöneticisi ve Sistem Özelleştirici güvenlik rollerinin varsayılan olarak yeni iş süreci akışlarına erişimi vardır.

   ![İş süreci akışına ayrıcalık atama](media/bpf-assign-privileges.png)

  Uygun radyo düğmelerini seçerek ayrıcalıkları belirtin ve Kaydet ' e tıklayın. Ayrıcalıklar hakkında daha fazla bilgi için bkz. [iş süreci akış ayrıcalıkları](business-process-flows-overview.md#BKMK_MultipleBPF).

  Daha sonra, güvenlik rolünü kuruluşunuzdaki uygun kullanıcılara atamayı unutmayın.

> [!TIP] 
>  Tasarımcı penceresinde görev akışınız üzerinde çalışırken göz önünde bulundurmanız gereken birkaç ipucu aşağıda verilmiştir:  
>   
> - İş süreci akışı penceresindeki her şeyin anlık görüntüsünü almak için eylem çubuğunda **anlık görüntü** ' yi seçin. Bu, örneğin, ekip üyelerinden işlem hakkında yorum almak ve bu işlemleri yapmak istiyorsanız yararlıdır.  
> - İşlemin farklı bölümlerine hızlıca gitmek için mini haritayı kullanın. Bu, ekranda kaydıran karmaşık bir işleminiz olduğunda faydalıdır.  
> - İş süreci için bir açıklama eklemek üzere iş süreci akışı penceresinin sol köşesindeki işlem adı altında **Ayrıntılar** ' ı seçin. En fazla 2000 karakter kullanabilirsiniz.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>İş süreci akışını düzenleme  
 İş süreci akışlarını düzenlemek için, Çözüm Gezgini ' ni açın, **işlemler**' i seçin ve ardından düzenlemek istediğiniz Işlem listesinden **iş süreci akışını** seçin.  
  
 İşlem listesinden düzenlemek istediğiniz iş süreci akışının adını seçtiğinizde, tasarımcı 'da açılır ve burada istediğiniz güncelleştirme yapabilirsiniz. Yeniden adlandırmak için işlem adının altındaki **ayrıntıları** genişletin veya bir açıklama ekleyin ve ek bilgileri görüntüleyin.  
  
 ![Bir iş süreci akışının genişletilmiş ayrıntılar bölümü](media/business-process-flow-details.png "Bir iş süreci akışının genişletilmiş ayrıntılar bölümü")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>İş süreci akışlarını öğrenmek için diğer şeyler
 **Aşamaları Düzenle**  
İş süreci akışları en fazla 30 aşamaya sahip olabilir.    
  
Bir aşamanın aşağıdaki özelliklerini ekleyebilir veya değiştirebilirsiniz:  
  
- **Aşama adı**  
  
- **Varlık**. Varlığı ilki dışında herhangi bir aşama için değiştirebilirsiniz.  
  
- **Aşama kategorisi**. Kategori, aşamaları bir eylem türüne göre gruplandırmanızı sağlar. Kayıtları içinde oldukları aşamaya göre gruplayarak raporlar için yararlıdır. Aşama kategorisi seçenekleri, aşama kategorisi genel seçenek kümesinden gelir. Bu genel seçenek kümesine daha fazla seçenek ekleyebilir ve isterseniz mevcut seçeneklerin etiketlerini değiştirebilirsiniz. İsterseniz de bu seçenekleri silebilirsiniz, ancak mevcut seçenekleri tutmanızı öneririz. Silerseniz, tam olarak aynı seçeneği geri ekleyemeyeceksiniz. Bunların kullanılmasını istemiyorsanız, etiketini "kullanma" olarak değiştirin.  
  
- **İlişki**. İşlemdeki önceki aşama farklı bir varlığa dayalı olduğunda bir ilişki girin. Şu anda tanımlanan aşama için, iki aşama arasında geçiş yaparken kullanılacak ilişkiyi tanımlamak için **Ilişkileri Seç** ' i seçin. Aşağıdaki avantajlar için bir ilişki seçmeniz önerilir:  
  
    -   İlişkiler genellikle kayıtlar arasında verileri otomatik olarak taşıyan, veri girişini en aza indirerek tanımlanmış öznitelik haritaları vardır.  
  
    -   Bir kayıt için işlem çubuğunda bir **sonraki aşama** ' ı seçtiğinizde, ilişkiyi kullanan tüm kayıtlar işlem akışında listelenecektir ve bu nedenle işlemdeki kayıtların yeniden kullanımını yükseltirsiniz. Ayrıca, iş akışlarını kullanarak, kullanıcının işlemi daha iyi kolaylaştırmak için bir kayıt oluşturmak yerine yalnızca bir tane seçmesi adına kayıtların oluşturulmasını otomatik hale getirebilirsiniz.  
  
**Adımları Düzenle**  
 Her aşamada en fazla 30 adım olabilir.    
  
**Dal Ekle**  
Bir aşamaya dal ekleme hakkında bilgi edinmek için bkz. [Dalla iş süreci akışlarını geliştirme](enhance-business-process-flows-branching.md).  
  
İş süreci akışını kişilerin kullanması için kullanılabilir hale getirmek için, işlem akışını sipariş etmeniz, güvenlik rollerini etkinleştirmeniz ve etkinleştirmeniz gerekir.  
  
**Işlem akış sırasını ayarla**  
 Bir varlık (kayıt türü) için birden fazla iş süreci akışınız olduğunda, hangi işlemin yeni kayıtlara otomatik olarak atandığını ayarlamanız gerekir. Komut çubuğunda, **sipariş Işlem akışı**' nı seçin. Yeni kayıtlar veya bunlarla ilişkili bir işlem akışı olmayan kayıtlar için, bir kullanıcının erişebileceği ilk iş süreci akışı kullanılacaktır.  
  
**Güvenlik rollerini etkinleştir**  
Kullanıcılar, kullanıcıya atanan güvenlik rolündeki iş süreci akışında tanımlanan ayrıcalığa bağlı olarak bir iş süreci akışına erişebilir. 

Varsayılan olarak, yalnızca **Sistem Yöneticisi** ve **Sistem Özelleştirici** güvenlik rolleri yeni bir iş süreci akışını görüntüleyebilir. 

Bir iş süreci akışındaki ayrıcalıkları belirtmek için, düzenleme için iş süreci akışını açın ve iş süreci akış Tasarımcısı 'nın komut çubuğunda **güvenlik rollerini Düzenle** ' yi seçin. Bu konuda daha önce listelenen [bir iş süreci akışı oluşturma](#create-a-business-process-flow) bölümünde 13. adıma bakın.
  
**Etkinleştir**  
Bir kişinin iş süreci akışını kullanabilmesi için, onu etkinleştirmeniz gerekir. Komut çubuğunda **Etkinleştir**' i seçin. Etkinleştirmeyi doğruladıktan sonra, iş süreci akışı kullanıma hazırdır. Bir iş süreci akışında hatalar varsa, hatalar düzeltilene kadar etkinleştiremeyeceksiniz.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>İş süreci akışına isteğe bağlı eylem ekleme
Dynamics 365 (çevrimiçi), sürüm 9,0 güncelleştirmesi bir iş süreci akış özelliği sunar: iş süreci akışı Otomasyonu, eylem adımları. Bir eylem veya iş akışını tetikleyecek bir iş süreci akışına düğme ekleyebilirsiniz.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Eylem adımını kullanarak isteğe bağlı iş akışları veya eylemler ekleme
Contoso kuruluşunun, fırsat niteliği sürecinin bir parçası olarak, tüm fırsatların belirlenmiş bir gözden geçiren tarafından gözden geçirilmesini gerektirdiğini varsayalım. Daha sonra contoso organizasyonu şu şekilde bir eylem oluşturdu: 

- Fırsat gözden geçiriciye atanan bir görev kaydı oluşturur. 
- Fırsat konusuna "incelemeye hazırlanıyor" ekler. 

Ayrıca, contoso 'nun bu eylemleri isteğe bağlı olarak çalıştırabilmeleri gerekir. Bu görevleri fırsat niteliği işlemi ile tümleştirmek için, eylemler iş süreci akışı 'nda görünür olmalıdır. Bu işlevi etkinleştirmek için **Iş süreci akışı eylem adımı olarak**öğesini seçin.
iş süreci akışı olarak çalışmak için kullanılabilir ![.](media/action-available-to-run.png)

Sonra, eylem adımı contoso 'un fırsat iş süreci akışına eklenir. Sonra işlem akışı onaylanır ve güncelleştirilir.

![Fırsat Iş süreci akışına eylem eklendi.](media/add-action-to-bpf.png)

Şimdi, contoso Salesforce üyeleri, **Çalıştır**' ı seçerek Iş sürecini uygun hale getirmek için, isteğe bağlı olarak **fırsat niteliğini Onayla** eylemini başlatabilir.

![Eylemi yürütün.](media/action-execute.png)

> [!IMPORTANT]
> - İsteğe bağlı bir eylem veya iş akışı yürütebilmek için, iş süreci akışı bir eylem adımını içermelidir. Eylem adımı bir iş akışı çalıştırıyorsa, iş akışının isteğe bağlı olarak çalışacak şekilde yapılandırılması gerekir.
> - Eylem veya iş akışıyla ilişkili varlık, iş süreci akışıyla ilişkili varlıkla aynı olmalıdır.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>İş süreci akışında eylem adımları kullanma sınırlaması

- Giriş veya çıkış parametreleri varlık, EntityCollection veya OptionSet (seçim listesi) türleridir, eylemler eylem adımları olarak kullanılamaz. Birden fazla EntityReference output parametresi veya herhangi bir sayıdaki EntityReference giriş parametresi olan eylemler eylem adımları olarak kullanılamaz. Birincil varlıkla ilişkilendirilmemiş eylemler (genel eylem) eylem adımları olarak kullanılamaz.

## <a name="instant-flows-in-business-process-flows"></a>İş süreci akışlarında anlık akışlar

Yinelenen görevleri otomatik hale getirmek, belge oluşturmak, onayları izlemek ve daha fazlasını bir iş sürecinde bir aşamanın içinden otomatikleştirmek için bir **anlık akış** çalıştırabilirsiniz.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>İş sürecinde bir adım olarak anlık akış ekleme

Size, yazıcı sattığımızı ve anlaşmaları kapatmak için **fırsat satışı Için müşteri adayı sürecini** kullandığınızı varsayalım. Bu işlemin bir parçası olarak, müşterinin müşteri ile paylaşmadan önce iş süreci akışının önceki bir aşamasında bir araya koyduğu teklifleri gözden geçirip onaylamasını sağlamak istersiniz.

Bunu yapmak için iki şey yapmanız gerekir:
1. Ekibin teklifinin gözden geçirilmesini ve onayını isteyen bir anlık akış oluşturun.
1. Anlık akışı, **fırsat satışları Için müşteri adayı sürecine**bir adım olarak ekleyin.

> [!TIP]
> İş sürecinde bir adım olarak yalnızca [çözüm kullanan akışlar](https://docs.microsoft.com/flow/overview-solution-flows) eklenebilir. 

### <a name="build-an-instant-flow"></a>Anlık akış oluşturma

1. Microsoft Flow ' de, gezinti menüsünde **çözümler** ' i seçin.
1. Görüntülenen çözümler listesinden **varsayılan çözümü** seçin. 
1. **+ Yeni** menüsünü seçin ve açılan listeden **akış** ' ı seçin.
1. İçin arama yapın ve ardından **Common Data Service** bağlayıcısını seçin.
1. ' İ arayın ve ardından **Common Data Service** Tetikleyicileri listesinden **bir kaydın ne zaman seçili bir** tetikleyiciyi seçin.
1. **Ortamı** **varsayılan**olarak ayarlayın ve ardından **varlık adı** ' nı **fırsat satışı sürecine müşteri adayı**olarak ayarlayın.
1. Kullanıcının teklife bağlantı girmesi için bir metin girişi alanı ekleyin.

   ![Anlık akış tetikleyicisi](media/instant-flow-trigger.png "Anlık akış tetikleyicisi")

   Onay isteği için bağlam sağlamaya yardımcı olmak üzere iş süreci akışı örneğinden bilgilere ihtiyacımız olacak, bu sayede bunu yapmak için bu adımları izleyin.

1. **JSON ayrıştırma** eylemini ekleyin. 
1. **Bir kaydın seçildiği** tetikleyici için dinamik değerler listesinden seçerek **içeriği** **varlığa** ayarlayın.
1. Aşağıdaki içeriği **şema** alanına yapıştırın.

    ```json
    {
        "type": "object",
        "properties": {
        "entity": {
            "type": "object",
            "properties": {
                "FlowsWorkflowLogId": {
                    "type": "string"
                },
                "BPFInstanceId": {
                    "type": "string"
                },
                "BPFInstanceEntityName": {
                    "type": "string"
                },
                "BPFDefinitionId": {
                    "type": "string"
                },
                "BPFDefinitionEntityName": {
                    "type": "string"
                },
                "StepId": {
                    "type": "string"
                },
                "BPFDefinitionName": {
                    "type": "string"
                },
                "BPFInstanceName": {
                    "type": "string"
                },
                "BPFFlowStageLocalizedName": {
                    "type": "string"
                },
                "BPFFlowStageEntityName": {
                    "type": "string"
                },
                "BPFFlowStageEntityCollectionName": {
                    "type": "string"
                },
                "BPFFlowStageEntityRecordId": {
                    "type": "string"
                },
                "BPFActiveStageId": {
                    "type": "string"
                },
                "BPFActiveStageEntityName": {
                    "type": "string"
                },
                "BPFActiveStageLocalizedName": {
                    "type": "string"
                }
            }
          }
        }
   }
   ```

   Bunlar şöyle görünmelidir:

   ![JSON Ayrıştır](media/instant-flow-json-date.png "JSON Ayrıştır")

  1. **Common Data Service** bağlayıcısından **kayıt al** eylemini ekleyin.
  1. **Ortamı** **(geçerli)** , **fırsat satış işlemine yol**açacak **varlık adını** ve **Bpfflowstageentityrecordıd**için **öğe tanımlayıcısını** ayarlayın.

     ![Kayıt ekleme](media/instant-flow-add-record.png)

     Artık verilere sahip olduğumuz **bir onay (v2)** eylemi ekleyerek ve ardından ilgili bilgileri doldurarak onay sürecini tanımlayın. Bilginiz yoksa [onaylar]( sequential-modern-approvals.md) hakkında daha fazla bilgi edinin.

     > [!TIP]
     > - **Kayıt al** eyleminden alanlar eklemek için dinamik içerik seçiciyi kullanın. böylece, onaylayanların isteğin ne olduğunu kolayca bilmesi için onay isteğine ilgili bilgileri ekleyin. 
     > - İş sürecinin içinde olduğu etkin aşama hakkında daha fazla bağlam sağlamak için, dinamik değerler listesinden **BPFActiveStageLocalizedName** alanını ekleyin.

     **Başlangıç ve onay için bekleme (v2)** kartı şuna benzer görünebilir:

      ![Onay kartı](media/instant-flow-add-approval-action.png)

1. Son olarak, akışı kaydedin ve sonra açın.

### <a name="add-this-flow-as-a-step-in-the-lead-to-opportunity-sales-process"></a>Bu akışı, fırsat satışı için müşteri adayı sürecine bir adım olarak ekleyin.

Artık anlık akışı oluşturduğunuza göre, gerekli olan tüm bunlar iş süreci akışınıza eklemektir. 

1. İş süreci akışı tasarımcısında **fırsat satışları Için müşteri adayı sürecini** açın. 
1. **Bileşenler** listesinden **akış adımını (Önizleme)** , **teklif** aşamasına sürükleyin ve bırakın.
1. Ardından, bir iş süreci akışına eklenebilen Tüm akışları listelemek için **Akış Seç** alanındaki arama simgesini seçin.
1. Listeden bir akış seçin ve ardından Özellikler bölmesinin altındaki **Uygula** düğmesini seçerek yaptığınız değişiklikleri kaydedin.
1. Son olarak, bu iş sürecini kullanıcılarınıza sunulan yeni bir anlık akış adımıyla akışa almak için **Güncelleştir** düğmesini seçin.
  
## <a name="next-steps"></a>Sonraki adımlar

 - [İş işleme akışlarına genel bakış](business-process-flows-overview.md)  
 - [Dalla iş süreci akışlarını geliştirin](enhance-business-process-flows-branching.md)
 - [Onayları genel bakış](sequential-modern-approvals.md)
 - [İş süreci akışına anlık akış ekleme hakkında ayrıntılı adımlar](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


