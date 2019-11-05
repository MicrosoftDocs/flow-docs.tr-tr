---
title: Verileri filtreleme ve kopyalama | Microsoft Docs
description: Microsoft Flow ile verileri filtreleyip hedefe kopyalamayı öğrenin
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
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: be5863c51e17bdba32d79891725a81b386ec2e90
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548920"
---
# <a name="filter-and-copy-data-with-microsoft-flow"></a>Microsoft Flow ile verileri filtreleme ve kopyalama
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bu izlenecek yol, yeni veya değiştirilmiş öğeler için bir kaynağı izleyen ve sonra bu değişiklikleri bir hedefe kopyalayan bir akışın nasıl oluşturulacağını gösterir. Kullanıcılarınız tek bir konuma veri girdiğinden, ancak ekibiniz farklı bir konuma veya biçimde bir konuma ihtiyaç duyuyorsa bu gibi bir akış oluşturabilirsiniz.

Bu izlenecek yol, verileri bir Microsoft SharePoint [listesinden](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) (kaynak) BIR [Azure SQL veritabanı](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) tablosuna (hedef) kopyalarken, Microsoft Flow tarafından desteklenen 150 ' den fazla [hizmetlerden](https://flow.microsoft.com/connectors/) herhangi biri arasında veri kopyalayabilirsiniz.

> [!IMPORTANT]
> İki yönlü eşitlemeler desteklenmediğinden hedefte yaptığınız değişiklikler kaynağa kopyalanmaz. İki yönlü bir eşitleme ayarlamaya çalışırsanız, değişikliklerin kaynak ve hedef arasında gereksiz şekilde gönderildiği sonsuz bir döngü oluşturacaksınız.
> 
> 

## <a name="prerequisites"></a>Kaynakları
* Bir veri kaynağına ve hedefe erişim. Bu izlenecek yol, kaynak ve hedef oluşturmak için gereken adımları içermez.
* [Microsoft Flow](https://flow.microsoft.com)erişim.
* Verilerinizin nasıl depolandığını temel olarak anlamak.
* Akış oluşturma hakkında temel bilgiler. [Eylemlerin, tetikleyicilerin](multi-step-logic-flow.md#add-another-action)ve [koşulların](add-condition.md)nasıl ekleneceğini gözden geçirebilirsiniz. Aşağıdaki adımlarda, bu eylemlerin nasıl gerçekleştirileceğini bildiğiniz varsayılmaktadır.

> [!TIP]
> Kaynak ve hedefteki her sütun adının eşleşmesi gerekmez, ancak bir öğeyi eklediğinizde veya güncelleştirdiğinizde *gerekli* tüm sütunlara veri sağlamalısınız. Microsoft Flow, sizin için gerekli alanları tanımlar.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Adımlara hızlı genel bakış
Microsoft Flow rahat kullanıyorsanız, verileri bir veri kaynağından diğerine kopyalamak için bu hızlı adımları kullanın:

1. İzlediğiniz kaynağı ve değiştirilen verileri kopyalayacaksınız hedefini belirler. Her ikisine de erişiminizin olduğunu onaylayın.
2. Kaynak ve hedefteki öğeleri benzersiz bir şekilde tanımlayan en az bir sütun belirler. Aşağıdaki örnekte **başlık** sütununu kullanıyoruz, ancak istediğiniz herhangi bir sütunu (ler) kullanabilirsiniz.
3. Kaynağı değişiklikler için izleyen bir tetikleyici ayarlayın.
4. Değiştirilen öğenin mevcut olup olmadığını öğrenmek için hedefte arama yapın.
5. Şöyle bir **koşul** kullanın:
   * Yeni veya değiştirilmiş öğe hedefte yoksa, onu oluşturun.
   * Hedefte yeni veya değiştirilmiş öğe varsa, güncelleştirin.
6. Akışınızı tetikleyin ve sonra yeni veya değiştirilmiş öğelerin kaynaktan hedefe kopyalandığını doğrulayın.

> [!NOTE]
> Daha önce SharePoint veya Azure SQL veritabanı ile bağlantı oluşturmadıysanız, oturum açmanız istendiğinde yönergeleri izleyin.
> 
> 

Akışı oluşturmak için ayrıntılı adımlar aşağıda verilmiştir.

## <a name="monitor-the-source-for-changes"></a>Kaynağı değişiklikler için izleme
1. [Microsoft Flow](https://flow.microsoft.com)oturum açın, **akışlarımı** boş > **Oluştur**' u seçin.
2. **SharePoint** 'i arayın > **SharePoint-bir öğe oluşturulduğunda veya** tetikleyici listesinden tetikleyici değiştirildiğinde SharePoint 'i seçin.
3. **Site adresini** girin ve ardından **bir öğe oluşturulduğunda veya değiştirildiğinde** kart üzerindeki **liste adını** seçin.
   
    Yeni veya güncelleştirilmiş öğeler için akış izleyicilerini SharePoint listesi için **site adresi** ve **liste adı** ' nı girin.
   
    ![SharePoint tetikleyicisini yapılandırma](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Hedefi yeni veya değiştirilmiş öğe için ara
Yeni veya değiştirilmiş öğe için hedefi aramak üzere **SQL Server-satırları al** eylemini kullanıyoruz.

1. **Eylem eklemek** > **yeni adım** ' ı seçin.
2. **Satırları al**' ı arayın, **SQL Server al satırları**' nı seçin ve ardından **tablo adı** listesinden izlemek istediğiniz tabloyu seçin.
3. **Gelişmiş seçenekleri göster**' i seçin.
4. **Filtre sorgusu** kutusuna **başlık EQ '** girin, dinamik içerik listesinden **başlık** belirtecini seçin ve ardından **'** i girin.
   
    Önceki adımda, kaynak ve hedefteki satırların başlıklarını eşleştirdiğinizi varsayar.
   
    **Satırları al** kartı şimdi şöyle görünmelidir:
   
    ![hedef veritabanından öğeyi almayı deneyin](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Yeni veya değiştirilmiş öğenin bulunup bulunmadığını denetle
**Koşul kartını açmak** Için **koşul eklemek** > **yeni adım** ' ı seçin.

Koşul kartında:

1. Sol taraftaki kutuyu seçin.
   
    **Bu akış listesinde kullanılan uygulamalardan ve bağlayıcılardan dinamik Içerik Ekle** açılır.
2. **Satırları al** kategorisinden **değer** ' i seçin.
   
   > [!TIP]
   > **Satırları al** kategorisinden **değer** seçtiğinizden emin olun. **Bir öğe oluşturulduğunda veya değiştirildiğinde** kategorisinden **değer** seçmeyin.
   > 
   > 
3. Orta kutudaki listeden **eşittir** ' i seçin.
4. Sağ taraftaki kutuya **0** (sıfır) girin.
   
    **Koşul** kartı şimdi şu resme benzer:
   
    ![koşul yapılandırma](media/odata-filters/configure-condition.png)
5. **Gelişmiş modda Düzenle '** yi seçin.
   
    Gelişmiş mod açıldığında, **\@Equals görürsünüz (gövde (' Get_rows ')? [' kutusundaki değer '], 0)** ifadesi. Body (' Get_items ') çevresine **length ()** ekleyerek bu ifadeyi düzenleyin **? [' Value ']** işlevi. İfadenin tamamı şu şekilde görünür: **@equals(length (' Get_rows ')? [' değer ']), 0)**
   
    **Koşul** kartı şimdi şu resme benzer:
   
    ![koşul yapılandırma](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > **Length ()** işlevinin eklenmesi, akışın **değer** listesini denetlemesini ve herhangi bir öğe içerip içermediğini belirlemesine izin verir.
   > 
   > 

Akışınız hedefteki öğeleri "aldığında", olası iki sonuç vardır.

| Sonucu | Sonraki adım |
| --- | --- |
| Öğe var |[Öğeyi güncelleştir](odata-filters.md#update-the-item-in-the-destination) |
| Öğe yok |[Yeni öğe oluştur](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> Bu kartlar, akışta kullanılan Azure SQL veritabanı tablosundaki sütunların adlarını gösterdiğinden, daha sonra gösterilen satır **ekleme** ve **güncelleştirme satırı** kartlarının görüntüleri sizinkinden farklı olabilir.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Hedefte öğe oluşturma
Öğe hedefte yoksa, **SQL Server satırı ekle** eylemini kullanarak oluşturun.

**Koşulun** **Evet** :

1. **Eylem Ekle**' yi seçin, **Ekle satırı**araması yapın ve **SQL Server-satır ekle**' yi seçin.
   
    **Satır ekle** kartı açılır.
2. **Tablo adı** listesinden, yeni öğenin ekleneceği tabloyu seçin.
   
    **Satır ekle** kartı genişletilir ve seçili tablodaki tüm alanları görüntüler. Yıldız işareti (*) olan alanlar gereklidir ve satırın geçerli olması için doldurulması gerekir.
3. Doldurmak istediğiniz her alanı seçin ve verileri girin.
   
    Verileri el ile girebilir, **dinamik içerikten**bir veya daha fazla belirteç seçebilir ya da alanlara metin ve belirteçlerin herhangi bir birleşimini girebilirsiniz.
   
    **Satır ekle** kartı şimdi şu resme benzer:
   
    ![koşul yapılandırma](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Hedefteki öğeyi güncelleştir
Öğe hedefte varsa, değişikliklerle güncelleştirin.

1. **SQL Server-Update satırı** eylemi, **koşulun** **hiçbir** dalı yoksa öğesine ekleyin.
2. Tablonun alanlarını doldurmak için bu belgenin [öğe oluştur](odata-filters.md#create-the-item-in-the-destination) bölümünde yer alan adımları izleyin.
   
    ![ortamları görüntüle](media/odata-filters/update-row.png)
3. Sayfanın üst kısmında, akış **adı** kutusuna akışınız için bir ad girin ve ardından, akışı kaydetmek Için **akış oluştur** ' u seçin.
   
    ![akışınızı adlandırın](media/odata-filters/give-the-flow-a-name.png)

Artık, SharePoint listenizdeki bir öğe (kaynak) değiştiğinde, akış tetiklenir ve yeni bir öğe ekler ya da Azure SQL veritabanınızda (hedef) var olan bir öğeyi güncelleştirir.

> [!NOTE]
> Kaynaktan bir öğe silindiğinde, akışınız tetiklenmez. Bu önemli bir senaryodur, bir öğenin artık gerekli olmadığını belirten ayrı bir sütun eklemeyi düşünün.
> 
> 

## <a name="learn-more"></a>Daha fazla bilgi edinin
Akışlarınızda [veri işlemlerini](data-operations.md) kullanın.

