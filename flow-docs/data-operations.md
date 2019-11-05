---
title: Veri işlemlerini anlama | Microsoft Docs
description: HTML tablosu oluşturma, CSV tablosu oluşturma, oluşturma, JOIN, seçme ve Microsoft Flow diziyi filtreleme gibi işlemleri gerçekleştirmeyi öğrenin.
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
ms.openlocfilehash: 87d805fb7de5ee9688e9e89c201be00fda8fb319
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547783"
---
# <a name="use-data-operations-with-microsoft-flow"></a>Microsoft Flow ile veri işlemlerini kullanma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bu kılavuzda, akış oluştururken verileri işlemek için kullanılabilen, oluşturma, katma, seçme, filtre dizisi, tablo oluşturma ve JSON ayrıştırma gibi Microsoft Flow popüler veri işlemlerinden bazılarını öğreneceksiniz.

## <a name="prerequisites"></a>Kaynakları
* Microsoft Flow erişim.
* Akışa bir JSON dizisi ile HTTP POST istekleri göndermek için [Postman](https://www.getpostman.com/postman) gibi bir araç.

## <a name="use-the-compose-action"></a>Oluşturma eylemini kullanma
Bir akış tasarlarken aynı verileri birden çok kez girmekten kazanmak için **veri işlemleri-oluşturma** (oluşturma) eylemini kullanın. Örneğin, akışınızı tasarlarken birkaç kez ````[0,1,2,3,4,5,6,7,8,9]```` bir basamak dizisi girmeniz gerekiyorsa, diziyi şöyle kaydetmek için oluşturma eylemini kullanabilirsiniz:

1. **Oluştur**' u arayın ve ardından **veri işlemleri-oluştur** (Oluştur) eylemini seçin.
   
    ![oluşturma eylemini arayın ve seçin](./media/data-operations/search-select-compose.png)
2. Daha sonra başvurmak istediğiniz **giriş** kutusuna diziyi girin:
   
    ![oluşturma eylemini yapılandırma](./media/data-operations/add-array-compose.png)

> [!TIP]
> Daha sonra daha kolay başvuru için, **oluşturma** kartının başlık çubuğunda bulunan "Oluştur" metnine tıklayarak **oluşturma** kartını yeniden adlandırın.
> 
> 

Oluşturma eyleminin içeriğine erişmeniz gerektiğinde, bu adımları izleyerek **Bu akış listesinde kullanılan uygulamalardan ve bağlayıcılardan dinamik Içerik Ekle** ' de **Çıkış** belirteci aracılığıyla bunu yapın:

1. **Veri işlemleri – JOIN**gibi bir eylem ekleyin.
2. Oluşturma eyleminde kaydettiğiniz içerikleri eklemek istediğiniz denetimi seçin.
   
    **Bu akışta kullanılan uygulamalardan ve bağlayıcılardan dinamik Içerik Ekle** açılır.
3. **Bu akışta kullanılan uygulamalardan ve bağlayıcılardan dinamik Içerik Ekle**' de, **dinamik içerik** sekmesinin **Oluştur** kategorisi altında bulunan **Çıkış** belirtecini seçin.
   
    ![oluşturma eyleminden çıkış kullanma](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>JOIN eylemini kullanma
Bir diziyi tercih ettiğiniz bir ayırıcıyla sınırlandırmak için **veri işlemleri-Birleştir** eylemini (JOIN) kullanın. Örneğin, akışlarınızın şu e-posta adresi dizisini içeren bir Web isteği aldığını varsayalım: ````["d@example.com", "k@example.com", "dal@example.com"]````. Ancak, e-posta programınız adreslerin noktalı virgülle ayrılmış tek bir dize olması gerekir. Bunu yapmak için, aşağıdaki adımları izleyerek virgül ayırıcısını noktalı virgül ";" olarak değiştirmek için **Data Operations-JOIN** (JOIN) eylemini kullanın:

1. Yeni bir eylem ekleyin, **JOIN**için arama yapın ve **veri işlemleri-Birleştir** (Birleştir) seçeneğini belirleyin.
   
    ![Birleştir eylemini arayın ve seçin](./media/data-operations/search-select-join.png)
2. **Kimden** kutusuna diziyi girin ve sonra da **birlikte bulunan** kutuya kullanmak istediğiniz yeni sınırlayıcıyı girin.
   
    Burada, noktalı virgül kullandım (;) Yeni sınırlayıcı olarak.
   
    ![JOIN eylemini yapılandırma](./media/data-operations/add-array-join.png)
3. Akışınızı kaydedin ve sonra çalıştırın.
4. Akışınız çalıştıktan sonra, **veri işlemleri – JOIN** eyleminin çıkışı şu şekilde olur:
   
    ![çıktıyı Birleştir](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Seçme eylemini kullanma
**Veri işlemlerini kullanın –** bir dizideki nesnelerin şeklini dönüştürmek için seçin (seçin). Örneğin, bir dizideki her bir nesnedeki öğeleri ekleyebilir, kaldırabilir veya yeniden adlandırabilirsiniz.

> [!NOTE]
> Seçme eylemini kullanarak öğe ekleyip kaldırabilmeniz sırasında dizideki nesne sayısını değiştiremezsiniz.
> 
> 

Örneğin, veri akışınızı bu biçimde bir Web isteği aracılığıyla girerse, select eylemini kullanabilirsiniz:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

"First" öğesini "FirstName", "Last" olarak yeniden adlandırarak ve "First" ve "Last" (boşluk ile ayrılmış) adlı yeni bir üye ekleyerek gelen verileri yeniden şekillendirmek istiyorsunuz:

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Bunu yapmak için:

1. Akışa **istek/yanıt – yanıt** (istek) eylemi ekleyin.
2. **İstek** kartından **şema oluşturmak Için örnek yük kullan** ' ı seçin.
3. Görüntülenen kutuya, kaynak veri diziniz örneğini yapıştırın ve ardından **bitti** düğmesini seçin.
4. **Veri işlemleri – Seç** (seçme) eylemini ekleyin ve ardından aşağıdaki görüntü gibi yapılandırın.
   
    ![Seçme eylemini yapılandırma](./media/data-operations/select-card.png)
   
   > [!TIP]
   > Seçim eyleminin çıktısı, yeni şekillendirilmiş nesneleri içeren bir dizidir. Daha sonra bu diziyi, daha önce açıklanan **oluşturma**gibi başka bir eylemde kullanabilirsiniz.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Diziyi filtrele eylemini kullanma
Bir dizideki nesne sayısını sağladığınız ölçütlerle eşleşen bir alt kümeyle azaltmak için **veri işlemleri-Filter Array** (filtre dizisi) kullanın.

> [!NOTE]
> Bir dizideki nesnelerin şeklini değiştirmek için filtre dizisi kullanılamaz. Ayrıca, üzerinde filtreleyebileceğiniz metin büyük/küçük harfe duyarlıdır.
> 
> 

Örneğin, bu dizide Filter Array kullanabilirsiniz:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

yalnızca *ilk* olarak "Deon" olarak ayarlanan nesneleri içeren yeni bir dizi oluşturmak için.

Bunu yapalim.

1. **Data Operations-Filter Array** (FILTER Array) eylemini bulun ve ardından akışınıza ekleyin.
2. Aşağıdaki görüntüde olduğu gibi filtre dizisi eylemini yapılandırın.
   
    ![filtre dizisi eylemini yapılandırma](./media/data-operations/add-configure-filter-array.png)
3. Akışınızı kaydedin ve daha sonra çalıştırın.
   
    Flow 'a JSON dizisi gönderen bir Web isteği oluşturmak için [Postman](https://www.getpostman.com/postman) kullanabilirsiniz.
4. Akışınız çalıştığında, JSON girişinin şu dizi gibi göründüğünü varsayarsak:
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    çıktı bu dizi gibi görünür (yalnızca *öncelikle* "Deon" olarak ayarlanmış olan nesnelerin eylemin çıktısına dahil edildiğini görürsünüz):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>CSV tablosu oluşturma eylemini kullanma
Bir JSON dizisi girişini virgülle ayrılmış değer (CSV) tablosuna dönüştürmek için **veri işlemleri-CSV tablosu oluşturma** (CSV tablosu oluşturma) kullanın. İsteğe bağlı olarak, CSV çıkışında üstbilgileri görünür tutabilirsiniz. Örneğin, **CSV tablosu oluştur** eylemini kullanarak aşağıdaki DIZIYI bir CSV tablosuna dönüştürebilirsiniz:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Aşağıdaki görüntüye benzemesi için **veri işlemleri-CSV tablosu oluştur** eylemini bulun, ekleyin ve yapılandırın.
   
    ![CSV tablosu oluşturma eylemini yapılandırma](./media/data-operations/create-csv-table.png)
   
    Note: Bu görüntüdeki **gövde** belirteci bir **istek/yanıt – yanıt** eyleminden gelir, ancak akıştaki herhangi BIR önceki eylemin çıktısından **CSV tablosu oluşturma** eyleminin girişini alabilir veya doğrudan **Kimden** kutusu.
2. Akışınızı kaydedin ve daha sonra çalıştırın.
   
    Akışınız çalıştığında, **CSV tablosu oluştur** çıktısı şu görüntüye benzer şekilde görünür:
   
    ![CSV tablo çıkışı oluştur](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>HTML tablosu oluştur eylemini kullanın
**Veri işlemleri-HTML tablosu oluşturma-** bir JSON dizisi GIRIŞINI bir HTML tablosuna dönüştürmek için kullanın. İsteğe bağlı olarak, HTML çıkışında üstbilgileri görünür tutabilirsiniz.

Bunu yapmak için, ayrıntılı bir örnek için [CSV tablosu oluşturma bölümündeki](#use-the-create-csv-table-action) adımları izleyin. Veri işlemleri- **CSV tablosu oluşturma** eylemi yerine **VERI işlemleri-HTML tablosu oluştur** eylemini kullandığınızdan emin olun.

> [!TIP]
> HTML tablosunu e-posta yoluyla göndermeyi planlıyorsanız, e-posta eyleminde "IsHtml" seçeneğini belirtmeyi unutmayın.
> 
> 

