---
title: "Koşullu ifadeler kullanma | Microsoft Docs"
description: "Aşağıdaki gibi gelişmiş ifadeler kullanma "
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
ms.openlocfilehash: a833abf7cb43e6d8a1c67b0f4160c90a4b24545a
ms.sourcegitcommit: 01325305b9d2cf964acac9feb6cca0af66db7440
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2017
---
# <a name="use-expressions-in-conditions-to-check-multiple-values"></a>Koşullarda ifadeleri kullanarak birden çok değeri denetleme
Bu kılavuzda, **Gelişmiş mod**’da ifadeleri ve **Koşulları** kullanarak birden çok değeri nasıl karşılaştırabileceğinizi öğreneceksiniz.

Bir akış oluştururken, temel moddaki [**Koşul**](add-condition.md#add-a-condition) kartını kullanarak tek bir değeri başka bir değerle hızlıca karşılaştırabilirsiniz. Ancak birden çok değeri karşılaştırmanızı gerektiren durumlar olabilir. Örneğin, bir elektronik tablodaki veya veritabanı tablosundaki birkaç sütunun değerlerini denetlemek isteyebilirsiniz.

Koşullarınızda aşağıdaki mantıksal ifadelerin herhangi bir birleşimini kullanabilirsiniz.

İfade|Açıklama|Örnek
--------|-----------|-------
|[and](#use-the-and-expression)|İki bağımsız değişkeni alır ve iki değer de true ise, true değerini döndürür.<br><b>Not</b>: İki bağımsız değişkenin de Boolean olması gerekir.|Bu ifade false değerini döndürür: <br>and(greater(1,10),equals(0,0))
|[or](#use-the-or-expression)|İki bağımsız değişkeni alır ve ikisinden biri true ise, true değerini döndürür. <br><b>Not</b>: İki bağımsız değişkenin de Boolean olması gerekir.|Bu ifade true değerini döndürür:<br>or(greater(1,10),equals(0,0))
|equals|İki değer eşitse true değerini döndürür.|Örneğin, parametre1’in değeri birDeğer olduğunda bu ifade true değerini döndürür:<br>equals(parameters('parametre1'), 'birDeğer')
|[less](#use-the-less-expression)|İki bağımsız değişkeni alır ve ilk bağımsız değişken ikincisinden küçükse true değerini döndürür. <br><b>Not</b>: Desteklenen türler integer, float ve string’dir.|Bu ifade true değerini döndürür:<br>less(10,100)
|lessOrEquals|İki bağımsız değişkeni alır ve ilk bağımsız değişken ikincisinden küçükse veya ikincisine eşitse true değerini döndürür. <br><b>Not</b>: Desteklenen türler integer, float ve string’dir.|Bu ifade true değerini döndürür:<br>lessOrEquals(10,10)
|[greater](#use-the-greater-expression)|İki bağımsız değişkeni alır ve ilk bağımsız değişken ikincisinden büyükse true değerini döndürür. <br><b>Not</b>: Desteklenen türler integer, float ve string’dir.|Bu ifade false değerini döndürür:<br>greater(10,10)
|greaterOrEquals|İki bağımsız değişkeni alır ve ilk bağımsız değişken ikincisinden büyük veya ikincisine eşitse true değerini döndürür. <br><b>Not</b>: Desteklenen türler integer, float ve string’dir.|Bu ifade false değerini döndürür:<br>greaterOrEquals(10,100)
|[empty](#use-the-empty-expression)|Nesne, dizi veya dize boşsa true değerini döndürür.|Bu ifade true değerini döndürür:<br>empty('')
|not|İki bağımsız değişkeni alır ve bunlar false ise true değerini döndürür. <br><b>Not</b>: İki bağımsız değişkenin de Boolean olması gerekir.|Bu ifade true değerini döndürür:<br>not(contains('200 Success','Fail'))
|if|İfadenin true veya false olarak sonuçlanmasına bağlı olarak belirli bir değeri döndürür.|Bu ifade "yes" değerini döndürür:<br>if(equals(1, 1), 'evet', 'hayır')

## <a name="prerequisites"></a>Önkoşullar
* Microsoft Flow erişimi.
* Bu kılavuzun sonraki bölümlerinde açıklanacak tabloları içeren bir elektronik tablo. Microsoft Flow’un elektronik tablolarınıza erişebilmesi için bunları Dropbox veya Microsoft OneDrive gibi bir konuma kaydettiğinizden emin olun.
* Microsoft Office 365 Outlook (Biz Office 365 Outlook kullanıyoruz, ancak siz akışlarınızda, desteklenen e-posta hizmetlerinden dilediğinizi kullanabilirsiniz.)

## <a name="use-the-or-expression"></a>Or ifadesini kullanma
Bazen, bir öğenin değerinin değerA **veya** değerB olmasına bağlı olarak iş akışınızın bir eylem gerçekleştirmesi gerekir. Örneğin, bir elektronik tablodaki görevlerin durumunu izliyor olabilirsiniz. Tablonun *Durum* adlı bir sütun içerdiğini ve *Durum* sütunundaki olası değerlerin şunlar olduğunu varsayalım:

* **tamamlandı**
* **engellendi**
* **gereksiz**
* **başlatılmadı**

Elektronik tablo şu örnekteki gibi görünebilir:

![örnek elektronik tablo](./media/use-expressions-in-conditions/spreadsheet-table.png)

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
4. Aşağıdaki **or** ifadesini ekleyin. Bu **or** ifadesi, tablodaki her satırın değerini denetler (satır, bir ifadede erişildiğinde öğe olarak bilinir). **Durum** sütunundaki değerin *tamamlandı* **veya** *gereksiz* olması durumunda, **or** ifadesi "true" olarak değerlendirilir.
   
    **or** ifadesi burada gösterildiği gibi görünür:
   
    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````
   
    **Koşul** kartınız şu resme benzer şekilde görünür:
   
    ![or ifadesi görüntüsü](./media/use-expressions-in-conditions/or-expression.png)

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
   
    ![akışınızı kaydedin](./media/use-expressions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-expression"></a>Akışı or ifadesiyle çalıştırma
Akış kaydedildikten sonra çalışır. Bu kılavuzda daha önce gösterilen elektronik tabloyu oluşturduysanız, çalıştırma tamamlandıktan sonra bu elektronik tablo şöyle görünür:

![or ifadesi tamamlanır](./media/use-expressions-in-conditions/spreadsheet-table-after-or-expression-runs.png)

Durum sütununda "tamamlandı" veya "gereksiz" değerine sahip olan satırlardaki tüm verilerin silindiğine dikkat edin.

## <a name="use-the-and-expression"></a>And ifadesini kullanma
Bir elektronik tabloda iki sütunlu bir tablonuz olduğunu varsayalım. Sütun adları Durum ve Atandı olsun. Durum sütununun "engellendi", Atandı sütununun ise "Turgay Elmas" değerine sahip olduğu tüm satırları silmek istediğinizi düşünelim.  Bu görevi gerçekleştirmek için bu kılavuzda daha önce açıklanan tüm adımları izleyin, ancak **Koşul** kartını gelişmiş modda düzenlerken burada gösterilen **and** ifadesini kullanın:

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

**Koşul** kartınız şu resme benzer şekilde görünür:

![and ifadesi görüntüsü](./media/use-expressions-in-conditions/and-expression.png)

### <a name="run-the-flow-with-the-and-expression"></a>Akışı and ifadesiyle çalıştırma
Kılavuzu takip ettiyseniz, elektronik tablonuz şu resme benzer şekilde görünür:

![and çalıştırılmadan önce](./media/use-expressions-in-conditions/spreadsheet-table-before-and-expression-runs.png)

Akışınız çalıştırıldıktan sonra, elektronik tablonuz şu resme benzer şekilde görünür:

![and çalıştırıldıktan sonra](./media/use-expressions-in-conditions/spreadsheet-table-after-and-expression-runs.png)

## <a name="use-the-empty-expression"></a>Boş ifade kullanma
Artık elektronik tabloda birkaç boş satır olduğuna dikkat edin. Bunları kaldırmak için **empty** ifadesini kullanarak Atandı ve Durum sütunlarında metin olmayan tüm satırları belirleyin.

Bu görevi gerçekleştirmek için bu kılavuzun önceki kısmında yer alan **and ifadesini kullanma** bölümündeki tüm adımları izleyin, ancak **Koşul** kartını gelişmiş modda düzenlerken empty ifadesini şu şekilde kullanın:

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

**Koşul** kartınız şu resme benzer şekilde görünür:

![empty ifadesi görüntüsü](./media/use-expressions-in-conditions/empty-expression.png)

Akışınız çalıştırıldıktan sonra, elektronik tablo şu resme benzer şekilde görünür:

![empty çalıştırıldıktan sonra](./media/use-expressions-in-conditions/spreadsheet-table-after-empty-expression-runs.png)

Ek satırların tablodan kaldırıldığına dikkat edin.

## <a name="use-the-greater-expression"></a>greater ifadesini kullanma
İş arkadaşlarınız için beyzbol biletleri satın aldığınızı ve herkesin bilet parasını ödediğinden emin olmak için bir elektronik tablo kullandığınızı varsayalım. Tutarın tamamını ödemeyen herkese günlük olarak e-posta gönderen bir akışı kolayca oluşturabilirsiniz.

Tutarın tamamını ödemeyen çalışanları belirlemek için **greater** ifadesini kullanın. Daha sonra, ödemeyi tamamlamamış kişilere otomatik olarak iyi niyetli bir anımsatma e-postası gönderebilirsiniz.

Elektronik tablo şöyle görünür:

![elektronik tablonun görünümü](./media/use-expressions-in-conditions/tickets-spreadsheet-table.png)

Ödemesi gereken tutarın tamamını ödememiş tüm kişileri belirleyen **greater** ifadesi şu şekilde uygulanır:

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-expression"></a>less ifadesini kullanma
İş arkadaşlarınız için beyzbol biletleri satın aldığınızı ve herkesin kabul ettiği bir tarihe kadar bilet parasını ödediğinden emin olmak için bir elektronik tablo kullandığınızı varsayalım. Geçerli tarih ile son tarih arasında bir günden kısa süre kaldığında henüz tutarın tamamını ödememiş olan kişilere anımsatma e-postası gönderen bir akış oluşturabilirsiniz.

Doğrulanması gereken iki koşul olduğundan, **and** ifadesinin yanı sıra **less** ifadesini kullanın:

| Doğrulanacak koşul | kullanılacak ifade | Örnek |
| --- | --- | --- |
| Tutarın tamamı ödendi mi? |greater |@greater(item()?['Tutar'], item()?['Ödenen']) |
| Son tarihe bir günden kısa süre mi kaldı? |less |@less(item()?['SonTarih'], addDays(utcNow(),1)) |

## <a name="combine-the-greater-and-less-expressions-in-an-and-expression"></a>Bir and ifadesinde greater ve less ifadelerini birleştirme
Ödemesi gereken tutarın altında ödeme yapan çalışanları belirlemek için **greater** ifadesini kullanın ve geçerli tarih ile son ödeme tarihi arasındaki sürenin bir günden kısa olup olmadığını belirlemek **less** ifadesini kullanın. Daha sonra, **E-posta gönder** eylemini kullanarak son tarihe bir günden kısa süre kalmasına rağmen tutarın tamamını ödememiş kişilere iyi niyetli bir anımsatma e-postası gönderebilirsiniz.

Elektronik tablo şöyle görünür:

![elektronik tablonun görünümü](./media/use-expressions-in-conditions/spreadsheet-table-due-date.png)

Son ödeme tarihine bir günden kısa süre kalmasına rağmen tutarın tamamını ödememiş olan tüm kişileri belirleyen **and** ifadesinin uygulanması şu şekilde yapılır:

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="learn-more"></a>Daha fazla bilgi
Diğer [ifadeler](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language#functions) hakkında bilgi edinin

