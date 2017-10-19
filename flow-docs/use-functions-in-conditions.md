---
title: "Koşullu işlevleri kullanın. | Microsoft Docs"
description: "Aşağıdaki gibi gelişmiş işlevleri kullanma "
"\"and\"\",": 
"\"\"or\"\",": 
"\"\"empty\"\",": 
"\"\"less\"\"": 
and: 
"\"\"greater\"\"": 
with: 
microsoft: 
flow: 
conditions.": 
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/01/2017
ms.author: deonhe
ms.openlocfilehash: 26f8dd2f8f9c027584bba197d301e4c8a32b0857
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="use-functions-in-conditions-to-check-multiple-values"></a>Koşullarda işlevleri kullanarak birden çok değeri denetleme
Bu kılavuzda, **Gelişmiş mod**’da işlevleri ve **Koşulları** kullanarak birden çok değeri nasıl karşılaştırabileceğinizi öğreneceksiniz.

Bir akış oluştururken, temel moddaki [**Koşul**](add-a-condition.md#add-a-condition) kartını kullanarak tek bir değeri başka bir değerle hızlıca karşılaştırabilirsiniz. Ancak birden çok değeri karşılaştırmanızı gerektiren durumlar olabilir. Örneğin, bir elektronik tablodaki veya veritabanı tablosundaki birkaç sütunun değerlerini denetlemek isteyebilirsiniz.

Koşullarınızda aşağıdaki mantıksal işlevlerin herhangi bir birleşimini kullanabilirsiniz.

| İşlev | Açıklama | Örnek |
| --- | --- | --- |
| <a href="#use-the-and-function">and</a> |İki bağımsız değişkeni alır ve iki değer de true ise, true değerini döndürür.<br><b>Not</b>: İki bağımsız değişkenin de Boolean olması gerekir. |Bu işlev, false değerini döndürür: <br>and(greater(1,10),equals(0,0)) |
| <a href="#use-the-or-function">or</a> |İki bağımsız değişkeni alır ve ikisinden biri true ise, true değerini döndürür. <br><b>Not</b>: İki bağımsız değişkenin de Boolean olması gerekir. |Bu işlev, true değerini döndürür:<br>or(greater(1,10),equals(0,0)) |
| equals |İki değer eşitse true değerini döndürür. |Örneğin, parametre1’in değeri birDeğer olduğunda bu işlev true değerini döndürür:<br>equals(parameters('parametre1'), 'birDeğer') |
| <a href="#use-the-less-function">less</a> |İki bağımsız değişkeni alır ve ilk bağımsız değişken ikincisinden küçükse true değerini döndürür. <br><b>Not</b>: Desteklenen türler integer, float ve string’dir. |Bu işlev, true değerini döndürür:<br>less(10,100) |
| lessOrEquals |İki bağımsız değişkeni alır ve ilk bağımsız değişken ikincisinden küçükse veya ikincisine eşitse true değerini döndürür. <br><b>Not</b>: Desteklenen türler integer, float ve string’dir. |Bu işlev, true değerini döndürür:<br>lessOrEquals(10,10) |
| <a href="#use-the-greater-function">greater</a> |İki bağımsız değişkeni alır ve ilk bağımsız değişken ikincisinden büyükse true değerini döndürür. <br><b>Not</b>: Desteklenen türler integer, float ve string’dir. |Bu işlev, false değerini döndürür:<br>greater(10,10) |
| greaterOrEquals |İki bağımsız değişkeni alır ve ilk bağımsız değişken ikincisinden büyük veya ikincisine eşitse true değerini döndürür. <br><b>Not</b>: Desteklenen türler integer, float ve string’dir. |Bu işlev, false değerini döndürür:<br>greaterOrEquals(10,100) |
| <a href="#use-the-empty-function">empty</a> |Nesne, dizi veya dize boşsa true değerini döndürür. |Bu işlev, true değerini döndürür:<br>empty('') |
| not |İki bağımsız değişkeni alır ve bunlar false ise true değerini döndürür. <br><b>Not</b>: İki bağımsız değişkenin de Boolean olması gerekir. |Bu işlev, true değerini döndürür:<br>not(contains('200 Success','Fail')) |
| if |İfadenin true veya false olarak sonuçlanmasına bağlı olarak belirli bir değeri döndürür. |Bu işlev "evet" değerini döndürür:<br>if(equals(1, 1), 'evet', 'hayır') |

## <a name="prerequisites"></a>Önkoşullar
* Microsoft Flow erişimi.
* Bu kılavuzun sonraki bölümlerinde açıklanacak tabloları içeren bir elektronik tablo. Microsoft Flow’un elektronik tablolarınıza erişebilmesi için bunları Dropbox veya Microsoft OneDrive gibi bir konuma kaydettiğinizden emin olun.
* Microsoft Office 365 Outlook (Biz Office 365 Outlook kullanıyoruz, ancak siz akışlarınızda, desteklenen e-posta hizmetlerinden dilediğinizi kullanabilirsiniz.)

## <a name="use-the-or-function"></a>or işlevini kullanma
Bazen, bir öğenin değerinin değerA **veya** değerB olmasına bağlı olarak iş akışınızın bir eylem gerçekleştirmesi gerekir. Örneğin, bir elektronik tablodaki görevlerin durumunu izliyor olabilirsiniz. Tablonun *Durum* adlı bir sütun içerdiğini ve *Durum* sütunundaki olası değerlerin şunlar olduğunu varsayalım:

* **tamamlandı**
* **engellendi**
* **gereksiz**
* **başlatılmadı**

Elektronik tablo şu örnekteki gibi görünebilir:

![örnek elektronik tablo](./media/use-functions-in-conditions/spreadsheet-table.png)

Yukarıdaki tabloyu göz önünde bulundurarak, Microsoft Flow aracılığıyla *Durum* sütunu *tamamlandı* veya *gereksiz* olarak ayarlanmış olan tüm satırları kaldırmak istediğinizi düşünelim.

Akışı oluşturalım.

### <a name="start-with-a-blank-flow"></a>Boş bir akışla başlayın
1. [Microsoft Flow](https://flow.microsoft.com)'da oturum açın.
   
    ![Oturum açın](includes/media/modern-approvals/sign-in.png)
2. **Akışlarım** sekmesini seçin.
   
    ![Akışlarım sekmesini seçin](includes/media/modern-approvals/select-my-flows.png)
3. **Boş akış oluştur**’u seçin.
   
    ![Boş akış oluştur](includes/media/modern-approvals/blank-template.png)

### <a name="add-a-trigger-to-your-flow"></a>Akışınıza bir tetikleyici ekleyin
1. **Zamanlama** sözcüğünü arayın ve sonra **Zamanlama - Yinelenme** tetikleyicisini seçin
   
    ![zamanlama tetikleyicisi](includes/media/schedule-trigger/schedule-trigger.png)
2. Zamanlamayı günde bir kez çalışacak biçimde ayarlayın.
   
    ![zamanlamayı ayarlama](includes/media/schedule-trigger/set-schedule.png)

### <a name="select-the-spreadsheet-and-get-all-rows"></a>Elektronik tabloyu seçin ve tüm satırları alın
1. **Yeni adım** > **Eylem ekle** seçeneğini belirleyin.
   
    ![Yeni adım](includes/media/new-step/action.png)
2. **Satırlar** sözcüğünü arayın ve sonra **Excel - Satırları al**’ı seçin.
   
    Not: Kullanmakta olduğunuz elektronik tabloya karşılık gelen "satırları al" eylemini seçin. Örneğin, Google E-Tablolar’ı kullanıyorsanız **Google E-Tablolar - Satırları al**’ı seçin.
   
    ![Satırları al](includes/media/new-step/get-excel-rows.png)
3. **Dosya adı** kutusunda klasör simgesini seçin, verilerinizi içeren elektronik tabloya göz atın ve tabloyu seçin.
   
    ![elektronik tabloyu seçme](includes/media/new-step/select-spreadsheet.png)
4. **Tablo adı** listesinden verilerinizi içeren tabloyu seçin.
   
    ![tabloyu seçme](includes/media/new-step/select-table.png)

### <a name="check-the-status-column-of-each-row"></a>Her satırın durum sütununu denetleyin
1. **Yeni adım** > **Diğer** > **“Her birine uygula” ekle**’yi seçin.
   
    ![tabloyu seçme](includes/media/new-step/apply-to-each.png)
2. **Değer** belirtecini **Önceki adımlardan bir çıkış seçin** kutusuna ekleyin.
   
    ![tabloyu seçme](includes/media/apply-to-each/add-value-token.png)
3. **Koşul ekle** > **Gelişmiş modda düzenle**’yi seçin.
4. Şu **or** işlevini ekleyin. Bu **or** işlevi, tablodaki her satırın değerini denetler (satır, bir işlevde erişildiğinde öğe olarak bilinir). **Durum** sütunundaki değerin *tamamlandı* **veya** *gereksiz* olması durumunda, **or** işlevi "true" olarak değerlendirilir.
   
    **or** işlevi burada gösterildiği gibi görünür:
   
    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````
   
    **Koşul** kartınız şu resme benzer şekilde görünür:
   
    ![or işlevi resmi](./media/use-functions-in-conditions/or-function.png)

### <a name="delete-matching-rows-from-the-spreadsheet"></a>Eşleşen satırları elektronik tablodan silme
1. Koşulun **EVET İSE, HİÇBİR ŞEY YAPMA** dalında **Eylem ekle**'yi seçin.
2. **Satırı sil** ifadesini arayın ve sonra **Excel - Satır sil**’i seçin.
   
    ![satırı sil resmi](includes/media/new-step/select-delete-excel-row.png)
3. **Dosya adı** kutusunda, silmek istediğiniz verileri içeren elektronik tablo dosyasını arayın ve seçin.
4. **Tablo adı** listesinde, verilerinizi içeren tabloyu seçin.
5. **Satır kimliği** kutusuna **Satır kimliği** belirtecini girin.
   
    ![elektronik tablo dosyası](includes/media/new-step/delete-excel-row.png)

### <a name="name-the-flow-and-save-it"></a>Akışı adlandırın ve kaydedin
1. Akışınıza bir ad verin ve sonra **Akış oluştur** düğmesini seçin.
   
    ![akışınızı kaydedin](./media/use-functions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-function"></a>Akışı or işleviyle çalıştırma
Akış kaydedildikten sonra çalışır. Bu kılavuzda daha önce gösterilen elektronik tabloyu oluşturduysanız, çalıştırma tamamlandıktan sonra bu elektronik tablo şöyle görünür:

![or işlevi tamamlandı](./media/use-functions-in-conditions/spreadsheet-table-after-or-function-runs.png)

Durum sütununda "tamamlandı" veya "gereksiz" değerine sahip olan satırlardaki tüm verilerin silindiğine dikkat edin.

## <a name="use-the-and-function"></a>and işlevini kullanma
Bir elektronik tabloda iki sütunlu bir tablonuz olduğunu varsayalım. Sütun adları Durum ve Atandı olsun. Durum sütununun "engellendi", Atandı sütununun ise "Turgay Elmas" değerine sahip olduğu tüm satırları silmek istediğinizi düşünelim.  Bu görevi gerçekleştirmek için bu kılavuzda daha önce açıklanan tüm adımları izleyin, ancak **Koşul** kartını gelişmiş modda düzenlerken burada gösterilen **and** işlevini kullanın:

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

**Koşul** kartınız şu resme benzer şekilde görünür:

![and işlevi görüntüsü](./media/use-functions-in-conditions/and-function.png)

### <a name="run-the-flow-with-the-and-function"></a>Akışı and işleviyle çalıştırma
Kılavuzu takip ettiyseniz, elektronik tablonuz şu resme benzer şekilde görünür:

![and çalıştırılmadan önce](./media/use-functions-in-conditions/spreadsheet-table-before-and-function-runs.png)

Akışınız çalıştırıldıktan sonra, elektronik tablonuz şu resme benzer şekilde görünür:

![and çalıştırıldıktan sonra](./media/use-functions-in-conditions/spreadsheet-table-after-and-function-runs.png)

## <a name="use-the-empty-function"></a>empty işlevini kullanın
Artık elektronik tabloda birkaç boş satır olduğuna dikkat edin. Bunları kaldırmak için **empty** işlevini kullanarak Atandı ve Durum sütunlarında metin olmayan tüm satırları belirleyin.

Bu görevi gerçekleştirmek için bu kılavuzun önceki kısmında yer alan **and işlevini kullanma** bölümündeki tüm adımları izleyin, ancak **Koşul** kartını gelişmiş modda düzenlerken empty işlevini şu şekilde kullanın:

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

**Koşul** kartınız şu resme benzer şekilde görünür:

![empty işlevi görüntüsü](./media/use-functions-in-conditions/empty-function.png)

Akışınız çalıştırıldıktan sonra, elektronik tablo şu resme benzer şekilde görünür:

![empty çalıştırıldıktan sonra](./media/use-functions-in-conditions/spreadsheet-table-after-empty-function-runs.png)

Ek satırların tablodan kaldırıldığına dikkat edin.

## <a name="use-the-greater-function"></a>greater işlevini kullanma
İş arkadaşlarınız için beyzbol biletleri satın aldığınızı ve herkesin bilet parasını ödediğinden emin olmak için bir elektronik tablo kullandığınızı varsayalım. Tutarın tamamını ödemeyen herkese günlük olarak e-posta gönderen bir akışı kolayca oluşturabilirsiniz.

Tutarın tamamını ödemeyen çalışanları belirlemek için **greater** işlevini kullanın. Daha sonra, ödemeyi tamamlamamış kişilere otomatik olarak iyi niyetli bir anımsatma e-postası gönderebilirsiniz.

Elektronik tablo şöyle görünür:

![elektronik tablonun görünümü](./media/use-functions-in-conditions/tickets-spreadsheet-table.png)

Ödemesi gereken tutarın tamamını ödememiş tüm kişileri belirleyen **greater** işlevi şu şekilde uygulanır:

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-function"></a>less işlevini kullanma
İş arkadaşlarınız için beyzbol biletleri satın aldığınızı ve herkesin kabul ettiği bir tarihe kadar bilet parasını ödediğinden emin olmak için bir elektronik tablo kullandığınızı varsayalım. Geçerli tarih ile son tarih arasında bir günden kısa süre kaldığında henüz tutarın tamamını ödememiş olan kişilere anımsatma e-postası gönderen bir akış oluşturabilirsiniz.

Doğrulanması gereken iki koşul olduğundan, **and** işlevinin yanı sıra **less** işlevini kullanın:

| Doğrulanacak koşul | Kullanılacak işlev | Örnek |
| --- | --- | --- |
| Tutarın tamamı ödendi mi? |greater |@greater(item()?['Tutar'], item()?['Ödenen']) |
| Son tarihe bir günden kısa süre mi kaldı? |less |@less(item()?['SonTarih'], addDays(utcNow(),1)) |

## <a name="combine-the-greater-and-less-functions-in-an-and-function"></a>Bir and işlevinde greater ve less işlevlerini birleştirme
Ödemesi gereken tutarın altında ödeme yapan çalışanları belirlemek için **greater** işlevini kullanın ve geçerli tarih ile son ödeme tarihi arasındaki sürenin bir günden kısa olup olmadığını belirlemek **less** işlevini kullanın. Daha sonra, **E-posta gönder** eylemini kullanarak son tarihe bir günden kısa süre kalmasına rağmen tutarın tamamını ödememiş kişilere iyi niyetli bir anımsatma e-postası gönderebilirsiniz.

Elektronik tablo şöyle görünür:

![elektronik tablonun görünümü](./media/use-functions-in-conditions/spreadsheet-table-due-date.png)

Son ödeme tarihine bir günden kısa süre kalmasına rağmen tutarın tamamını ödememiş olan tüm kişileri belirleyen **and** işlevinin uygulanması şu şekilde yapılır:

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="learn-more"></a>Daha fazla bilgi
Diğer [işlevler](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language#functions) hakkında bilgi edinin

