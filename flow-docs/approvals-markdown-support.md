---
title: Microsoft Flow onaylarını biçimlendirmek için markaşağı kullanma | Microsoft Docs
description: Microsoft Flow onay isteklerini biçimlendirmek için markaşağı kullanmayı öğrenin.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b82ac7c53c8c018b5e61011e4c1d8b9cdabe9747
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545311"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Microsoft Flow onay isteklerinde Markaşağı kullanma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu makalede, onay istekleriniz için zengin biçimlendirme ve tablolar eklemek üzere [markın](https://en.wikipedia.org/wiki/Markdown) söz dizimini nasıl kullanabileceğiniz öğretilir.

## <a name="headers"></a>Bilgisinde

Üstbilgileri kullanarak yorumlarınızı yapısını yapın. Üst bilgiler segmenti daha uzun Yorumlar, daha kolay okunabilir hale getirir.

Bir başlık ayarlamak için karma karakter `#` bir satır başlatın. Ek karma karakterleri olan bir satır başlatarak (örneğin `####`) açıklamaları alt başlıklar ile düzenleyin. En fazla altı düzey başlık desteklenir.

**Örneğinde**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Kaynaklanan**

![Akışı dışarı aktar](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Paragraflar ve satır sonları

Paragraf veya satır sonları ile ayırarak metninizi daha kolay okunabilir hale getirin. Yeni bir paragrafa başlamak için satır sonundan önce iki boşluk girin veya yeni bir paragrafa başlamak için art arda iki satır sonu girin.   
   
**Örneğinde**

ENTER tuşu ile metninizdeki satırları ekleyin.
Bu, metninizi daha iyi ve okumayı kolaylaştırır.

**Sonuç:**    
ENTER tuşu ile metninizdeki satırları ekleyin.      
Bu, metninizi daha iyi ve okumayı kolaylaştırır.


**Örnek 2**

Satırın sonundan önce iki boşluk ekleyin. (boşluk, boşluk)     
Bu, paragraflar arasında boşluk ekler.

**Kaynaklanan**  
Satırın sonundan önce iki boşluk ekleyin.   

Bu, paragraflar arasında boşluk ekler.
  

## <a name="lists"></a>Liste

İlgili öğeleri listelerle düzenleyin. Numaralarla sıralı listeler veya yalnızca madde işaretleriyle sıralanmamış listeler ekleyebilirsiniz.

Sıralı listeler, her liste öğesi için bir sayı ile başlar. Sırasız listeler bir `*`başlar. Her liste öğesini yeni bir satırda başlatın. Bir Markaşağı dosyası veya pencere öğesinde, yeni bir paragrafa başlamak için satır sonundan önce iki boşluk girin veya yeni bir paragrafa başlamak için art arda iki satır sonu girin.   

### <a name="ordered-or-numbered-lists"></a>Sıralı veya numaralandırılmış listeler

**Örneğinde**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Kaynaklanan**

1. İlk öğe.
2. İkinci öğe.
3. Üçüncü öğe.

### <a name="bullet-lists"></a>Madde işareti listeleri

**Örneğinde**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Kaynaklanan**

- Öğe 1
- Öğe 2
- Öğe 3

### <a name="nested-lists"></a>İç içe listeler

**Örneğinde**
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

**Kaynaklanan**  

1. İlk öğe.

    - Öğe 1
    - Öğe 2
    - Öğe 3
2. İkinci öğe.
    - İç içe öğe 1
    - İç içe öğe 2
    - İç içe öğe 3


## <a name="links"></a>Köprü

HTTP ve HTTPS URL 'Leri otomatik olarak bağlantılar olarak biçimlendirilir. 

Standart markaşağı bağlantı sözdizimini kullanarak URL 'niz için metin köprüleri ayarlayabilirsiniz:

```Markdown
[Link Text](Link URL)
```

**Örneğinde**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Kaynaklanan**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Bağlantı bağlantıları

Yer işareti kimlikleri HTML olarak işlendiğinde tüm başlıklara atanır. Bu KIMLIK, boşluk (-) ve tüm küçük harf olarak değişen boşluklar içeren başlık metinidir.

**Örneğinde**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Kaynaklanan**

Bölüm için bir bağlama bağlantısı sözdizimi...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
KIMLIğIN hepsi küçük harfle indirilir ve bağlantı büyük/küçük harfe duyarlıdır; bu nedenle, başlığın kendisi büyük harf kullanıyor olsa da küçük harf ayrımına dikkat edin.


## <a name="tables"></a>Takvimleri

Yapılandırılmış verileri tablolarla düzenleyin. 

- Her tablo satırını kendi satırına yerleştir 
- Çizgi karakterini kullanarak tablo hücrelerini ayırın `|` 
- Tablonun ilk iki satırı, sütun üst bilgilerini ve tablodaki öğelerin hizalamasını ayarlar
- Sütun hizalamasını (sol, orta, sağ) belirtmek için tabloların üst bilgisini ve gövdesini bölmek için iki nokta üst üste (`:`) kullanın 
- Yeni bir satır başlatmak için HTML kesme etiketini (`<br/>`) kullanın (bir wiki içinde çalışmaz ancak başka bir yerde değil)  
- Her satırı CR veya LF ile sonlandırdığınızdan emin olun. 

**Örneğinde**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Kaynaklanan**  

| Başlık 1 | Başlık 2 | Başlık 3 |  
|-----------|:---------:|-----------:|  
| A1 hücresi | A2 hücresi | Hücre a3 |  
| Hücre B1 | B2 hücresi | Hücre B3<br/>metnin ikinci satırı |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Vurgu (kalın, italik, üstü çizili)  

Karakterleri kalın, italik veya üstü çizili olarak uygulayarak metni vurgulayabilirsiniz: 
- İtalik uygulamak için: metni bir yıldız işareti `*` veya alt çizgi ile çevreleyin `_`   
- Kalın uygulamak için: metni çift yıldız `**`çevreleyin.    
- Üstü çizili uygulamak için: metni çift tilde karakterlerle çevreleyin `~~`.   

Metne birden çok vurgu uygulamak için bu öğeleri birleştirin.    

**Örneğinde**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Kaynaklanan**

Açıklamalarda _vurgu_ kullanarak **güçlü** OPTA ve <s>düzeltme</s> noktaları hakkında bilgi edinin   
**_Kalın, italik metin_**    
**~~Kalın, çizili metin~~**  


## <a name="special-characters"></a>Özel karakterler

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Sözdizimi</th>
<th width="350px">Örnek/notlar</th>
</tr>



<tr>
<td>
<p>Aşağıdaki karakterlerden birini eklemek için ters eğik çizgiyle önek:</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>Özel karakterler ekleme hakkında bazı örnekler
<p>\\ almak için ```\\``` girin </p>
<p>_ Almak için ```\_``` girin </p>
<p>\# almak için ```\#``` girin </p>
<p>\( almak için ```\(``` girin </p>
<p>\. almak için ```\.``` girin </p>
<p>\! almak için ```\!``` girin </p>
</td>
</tr>

</tbody>
</table>
