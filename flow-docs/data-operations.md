---
title: Veri işlemlerini anlama | Microsoft Docs
description: Microsoft Flow ile HTML tablosu oluşturma, CSV tablosu oluşturma, dizi oluşturma, birleştirme, seçme ve diziyi filtreleme gibi eylemleri gerçekleştirmeyi öğrenin.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/02/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c28fa7feb743db4616199246d6d517e2e1f6aff9
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691011"
---
# <a name="use-data-operations-with-microsoft-flow"></a>Microsoft Flow ile veri işlemlerini kullanma
Bu kılavuzda, Microsoft Flow’un akış oluştururken verileri işlemek için kullanabileceğiniz dizi oluşturma, birleştirme, seçme, diziyi filtreleme, tablo oluşturma ve JSON dosyasını ayrıştırma gibi popüler veri işlemlerinden bazıları hakkında bilgi edineceksiniz.

## <a name="prerequisites"></a>Önkoşullar
* Microsoft Flow erişimi.
* Akışınıza JSON dizisi içeren HTTP POST istekleri göndermek için [PostMan](https://www.getpostman.com/postman) gibi bir araç.

## <a name="use-the-compose-action"></a>Oluşturma eylemini kullanma
Bir akış tasarlarken aynı verileri birden çok kez girmekten kaçınmak için **Veri İşlemleri - Oluştur** (oluşturma) eylemini kullanın. Örneğin, akışınızı tasarlarken ````[0,1,2,3,4,5,6,7,8,9]```` rakam dizisini birkaç kez girmeniz gerekiyorsa, oluşturma eylemini kullanarak diziyi şu şekilde kaydedebilirsiniz:

1. **Oluştur** sözcüğünü arayın ve sonra **Veri İşlemleri - Oluştur** (oluşturma) eylemini seçin.
   
    ![oluştur eylemini arayın ve seçin](./media/data-operations/search-select-compose.png)
2. Diziyi daha sonra başvurmak istediğiniz **Girişler** kutusuna girin:
   
    ![oluşturma eylemini yapılandırma](./media/data-operations/add-array-compose.png)

> [!TIP]
> Sonradan kolayca başvurabilmek için **Oluştur** kartının başlık çubuğundaki “Oluştur” metnine tıklayarak **Oluştur** kartını yeniden adlandırın.
> 
> 

Oluşturma eyleminin içeriğine erişmeniz gerekiyorsa, bunu aşağıdaki adımları izleyerek **Bu akışta kullanılan uygulama ve bağlayıcılardan dinamik içerik ekleyin** listesindeki **Çıkış** belirteci aracılığıyla gerçekleştirin:

1. **Veri İşlemleri – Birleştir** gibi bir eylem ekleyin.
2. Oluşturma eyleminde kaydettiğiniz içeriği hangi denetime eklemek istediğinizi seçin.
   
    **Bu akışta kullanılan uygulama ve bağlayıcılardan dinamik içerik ekleyin** listesi açılır.
3. **Bu akışta kullanılan uygulama ve bağlayıcılardan dinamik içerik ekleyin** listesinde, **Dinamik içerik** sekmesinin **Oluşturma** kategorisi altındaki **Çıkış** belirtecini seçin.
   
    ![oluşturma eyleminden alınan çıkışı kullanma](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>Birleştirme eylemini kullanma
Bir diziyi tercih ettiğiniz bir ayıraçla sınırlamak için **Veri İşlemleri - Birleştir** (Birleştirme) eylemini kullanın. Örneğin, akışınızın şu e-posta adresi dizisini içeren bir web isteği aldığını varsayalım: ````["d@example.com", "k@example.com", "dal@example.com"]````. Ancak e-posta programınız adreslerin noktalı virgüllerle ayrılmış tek bir dize olmasını gerektiriyor olsun. Bunu yapmak için aşağıdaki adımları izleyin ve **Veri İşlemleri - Birleştir** (birleştirme) eylemini kullanarak virgül olan sınırlayıcıyı noktalı virgül (“;”) olarak değiştirin:

1. Yeni bir eylem ekleyin, **Birleştir** sözcüğünü arayın ve **Veri İşlemleri - Birleştir** (birleştirme) seçeneğini belirleyin.
   
    ![birleştirme eylemini arama ve seçme](./media/data-operations/search-select-join.png)
2. Diziyi **Kimden** kutusuna girin ve sonra kullanmak istediğiniz yeni sınırlayıcıyı **Şununla birleştir** kutusuna girin.
   
    Burada, yeni sınırlayıcı olarak noktalı virgülü (;) kullandım.
   
    ![birleştirme eylemini yapılandırma](./media/data-operations/add-array-join.png)
3. Akışınızı kaydedin ve çalıştırın.
4. Akışınız çalıştıktan sonra, **Veri İşlemleri – Birleştirme** eyleminin çıkışı şu olur:
   
    ![birleştirme çıkışı](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Seçme eylemini kullanma
Bir dizideki nesnelerin biçimini dönüştürmek için **Veri İşlemleri – Seç** (seçme) eylemini kullanın. Örneğin, bir dizideki her nesnede öğe ekleyebilir, öğeleri kaldırabilir veya yeniden adlandırabilirsiniz.

> [!NOTE]
> Seçme eylemini kullanarak öğe ekleyip kaldırabilseniz de dizideki nesne sayısını değiştiremezsiniz.
> 
> 

Örneğin, veriler bir web isteği aracılığıyla akışınıza

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

biçiminde giriyorsa ve "first" değerini "FirstName" olarak, "last" değeriniyse "LastName" olarak değiştirmenin yanı sıra bir boşlukla ayrılmış "first" ve "last" değerlerini birleştiren "FamilyName" adlı yeni bir üye ekleyerek gelen verileri dönüştürmek istiyorsanız seçme eylemini kullanabilirsiniz:

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Bunu yapmak için:

1. Akışınıza **İstek/Yanıt – Yanıt** (istek) eylemini ekleyin.
2. **İstek** kartından **Şema oluşturmak için örnek yük kullan**’ı seçin.
3. Görüntülenen kutuda kaynak veri dizinizin bir örneğini yapıştırın ve **Bitti** düğmesini seçin.
4. **Veri İşlemleri – Seç** (seçme) eylemini seçin ve aşağıdaki resimde gösterildiği gibi yapılandırın.
   
    ![seçme eylemini yapılandırma](./media/data-operations/select-card.png)
   
   > [!TIP]
   > Seçme eyleminden alınan çıkış, yeni şekillendirilmiş nesneleri içeren bir dizidir. Daha sonra bu diziyi daha önce açıklandığı gibi başka bir eylemde (**Oluştur** gibi) kullanın.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Diziyi filtreleme eylemini kullanma
Bir dizideki nesne sayısını belirttiğiniz ölçütlerle eşleşen bir alt kümeye düşürmek için **Veri İşlemleri - Diziyi filtrele** (diziyi filtreleme) eylemini kullanın.

> [!NOTE]
> Diziyi filtreleme eylemi, bir dizideki nesnelerin şeklini değiştirmek için kullanılamaz. Ayrıca, filtre uyguladığınız metin büyük/küçük harfe duyarlıdır.
> 
> 

Örneğin, diziyi filtreleme eylemini

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

dizisinde kullanarak yalnızca *first* değerinin “Deon” olarak ayarlandığı nesneleri içeren yeni bir dizi oluşturabilirsiniz.

Haydi yapalım.

1. **Veri İşlemleri - Diziyi filtrele** (diziyi filtreleme) eylemini bulun ve akışınıza ekleyin.
2. Diziyi filtreleme eylemini aşağıdaki resimde görüldüğü gibi yapılandırın.
   
    ![diziyi filtreleme eylemini yapılandırma](./media/data-operations/add-configure-filter-array.png)
3. Akışınızı kaydedip çalıştırın.
   
    Akışınıza JSON dizisi gönderen bir web isteği oluşturmak için [PostMan](https://www.getpostman.com/postman) uygulamasını kullanabilirsiniz.
4. Akışınız çalıştığında, JSON girişinin
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````
   
    dizisi gibi göründüğünü varsayarsak çıkış şu dizideki gibi görünür (eylemin çıkışına yalnızca *first* değerinin “Deon” olarak ayarlandığı nesnelerin eklendiğine dikkat edin):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Csv tablosu oluşturma eylemini kullanma
Bir JSON dizisi girişini virgülle ayrılmış değer (CSV) tablosuna dönüştürmek için **Veri İşlemleri - CSV tablosu oluştur** (csv tablosu oluşturma) eylemini kullanın. İsteğe bağlı olarak, CSV çıkışında üst bilgilerin görünür kalmasını sağlayabilirsiniz. Örneğin, **CSV tablosu oluştur** eylemini kullanarak aşağıdaki diziyi bir CSV tablosuna dönüştürebilirsiniz:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. **Veri İşlemleri - CSV tablosu oluştur** eylemini bulun, ekleyin ve aşağıdaki resimdekine benzeyecek şekilde yapılandırın.
   
    ![csv tablosu oluşturma eylemini yapılandırma](./media/data-operations/create-csv-table.png)
   
    Not: Bu resimdeki **Gövde** belirteci bir **İstek/Yanıt – Yanıt** eyleminden gelir, ancak **CSV tablosu oluştur** eylemine yönelik girişi akışınızda daha önce gerçekleştirilen herhangi bir eylemden alabilir ya da doğrudan **Kimden** kutusuna girebilirsiniz.
2. Akışınızı kaydedip çalıştırın.
   
    Akışınız çalıştığında, **CSV tablosu oluştur** çıkışı şu resimdekine benzer:
   
    ![csv tablosu çıkışı oluşturma](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>Html tablosu oluşturma eylemini kullanma
Bir JSON dizisi girişini HTML tablosuna dönüştürmek için **Veri İşlemleri - HTML tablosu oluştur** eylemini kullanın. İsteğe bağlı olarak, HTML çıkışında üst bilgilerin görünür kalmasını sağlayabilirsiniz.

Bunu yapmak için [csv tablosu oluşturma bölümündeki](#use-the-create-csv-table-action) ayrıntılı örnek adımlarını izleyin. **Veri İşlemleri - CSV tablosu oluştur** eylemi yerine **Veri İşlemleri - HTML tablosu oluştur** eylemini kullandığınızdan emin olun.

> [!TIP]
> HTML tablosunu e-posta yoluyla göndermeyi planlıyorsanız, e-posta eyleminde "IsHtml" seçeneğini belirlemeyi unutmayın.
> 
> 

