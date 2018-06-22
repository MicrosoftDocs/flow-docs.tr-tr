---
title: Microsoft Flow onaylarını biçimlendirmek için markdown kullanma | Microsoft Docs
description: Microsoft Flow onay isteklerini biçimlendirmek için markdown kullanmayı öğrenin.
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
ms.openlocfilehash: dc8d9d650b02b7962770ff0574deb151492739d9
ms.sourcegitcommit: 87934a195701e2ab33127ee084b9519e387db268
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32323644"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Microsoft Flow onay isteklerinde Markdown kullanma

Bu makalede [Markdown](https://en.wikipedia.org/wiki/Markdown) söz dizimi kullanarak onay isteklerinize zengin biçimlendirme ve tablo ekleme öğretilir.

## <a name="headers"></a>Üst Bilgiler

Üst bilgileri kullanarak açıklamalarınızı yapılandırın. Üst bilgiler daha uzun açıklamalar oluşturarak okunmalarını daha kolay hale getirir.

Bir başlık ayarlamak için satıra kare karakteriyle `#` başlayın. Satıra `####` gibi ek kare karakterleriyle başlayarak açıklamalarınızı alt başlıklarla düzenleyin. En fazla altı düzeyde başlık desteklenir.

**Örnek:**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Sonuç:**

![Akışı dışarı aktarma](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Paragraflar ve satır sonları

Metninizi paragraflar ve satır sonlarıyla ayırarak daha kolay okunur hale getirin. Yeni bir paragrafa başlamak için satır sonundan önce iki boşluk girin veya art arda iki satır sonu girin.   
   
**Örnek**

<pre>
Add lines between your text with the Enter key.
This spaces your text better and makes it easier to read.
</pre>

**Sonuç:**   
Enter tuşuyla metninizin arasına satırlar ekleyin.      
Bu metninizde daha iyi bir şekilde aralıklar bırakarak metninizi okumayı kolaylaştırır.


**Örnek 2**

<pre>
Add two spaces prior to the end of the line.(space, space)     
This adds space in between paragraphs.
</pre>

**Sonuç:**  
Satır sonundan önce iki boşluk ekleyin.   

Bu işlem paragraflar arasında boşluk bırakır.
  

## <a name="lists"></a>Listeler

İlgili öğeleri listelerle düzenleyin. Numaralı sıralı listeler veya yalnızca madde işaretli sırasız listeler ekleyebilirsiniz.

Sıralı listeler her bir liste öğesinde bir sayı ve ardından bir noktayla başlar. Sırasız listeler `*` ile başlar. Her liste öğesine yeni bir satırda başlayın. Bir Markdown dosyası veya widget’ta, yeni bir paragrafa başlamak için satır sonundan önce iki boşluk girin veya art arda iki satır sonu girin.   

### <a name="ordered-or-numbered-lists"></a>Sıralı veya numaralı listeler

**Örnek:**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Sonuç:**

1. İlk öğe.
2. İkinci öğe.
3. Üçüncü öğe.

### <a name="bullet-lists"></a>Madde işareti listeleri

**Örnek:**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Sonuç:**

- Öğe 1
- Öğe 2
- Öğe 3

### <a name="nested-lists"></a>İç içe listeler

**Örnek:**
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

**Sonuç:**  

1. İlk öğe.

    - Öğe 1
    - Öğe 2
    - Öğe 3
2. İkinci öğe.
    - İç içe öğe 1
    - İç içe öğe 2
    - İç içe öğe 3


## <a name="links"></a>Bağlantılar

HTTP ve HTTPS URL’leri otomatik olarak bağlantı gibi biçimlendirilir. 

Standart markdown bağlantı söz dizimini kullanarak URL’niz için metin köprüleri ayarlayabilirsiniz:

```Markdown
[Link Text](Link URL)
```

**Örnek:**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Sonuç:**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Yer işareti bağlantıları

Yer işareti kimlikleri HTML olarak işlendiğinde tüm üst bilgilere atanır. Kimlik, boşlukların çizgilerle (-) değiştirildiği ve tüm harflerin küçük olduğu başlık metnidir.

**Örnek:**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Sonuç:**

Bir bölümün yer işareti bağlantısına ait söz dizimi...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
Kimliğin tüm harfleri küçük ve bağlantı büyük/küçük harfe duyarlı olduğundan, başlığın kendisi büyük harf kullansa bile küçük harf kullandığınızdan emin olun.


## <a name="tables"></a>Tablolar

Yapılandırılmış verileri tablolarla düzenleyin. 

- Her tablo satırını kendi satırına yerleştirin 
- Dikey çubuk karakterini `|` kullanarak tablo hücrelerini ayırın 
- Tablodaki ilk iki satır, sütun üst bilgilerini ve tablodaki öğelerin hizalarını ayarlar
- Sütun hizasını (sol, orta, sağ) belirlemek için tabloların üst bilgi ve gövdesini bölerken iki nokta (`:`) kullanın 
- Yeni bir satıra başlatmak için HTML sonu etiketi (`<br/>`) kullanın (Wiki dışında başka yerde çalışmaz)  
- Her satırı bir CR veya LF ile sonlandırdığınızdan emin olun. 

**Örnek:**

<pre>
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
</pre>  <br/>

**Sonuç:**  

| Başlık 1 | Başlık 2 | Başlık 3 |  
|-----------|:---------:|-----------:|  
| Hücre A1 | Hücre A2 | Hücre A3 |  
| Hücre B1 | Hücre B2 | Hücre B3<br/>metnin ikinci satırı |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Vurgu (kalın, italik, üstü çizili)  

Karakterlere kalın, italik veya üstü çizgili biçimler uygulayarak metni vurgulayabilirsiniz: 
- İtalik stil uygulamak için: metnin başına ve sonuna bir yıldız işareti `*` veya alt çizgi `_` koyun   
- Kalın stil uygulamak için: metnin başına ve sonuna çift yıldız `**` koyun.    
- Üstü çizili stil uygulamak için: metnin başına ve sonuna çift tilde karakteri `~~` koyun.   

Metne birden çok vurgu uygulamak için bu öğeleri birleştirin.    

**Örnek:**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Sonuç:**

Açıklamalarda _vurgu_ kullanarak **güçlü** fikirlerinizi ifade edin ve <s>düzeltmeleri</s>  belirtin  
**_Kalın, italik metin_**   
**~~Kalın, üstü çizgili metin~~**  


## <a name="special-characters"></a>Özel karakterler

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Söz dizimi</th>
<th width="350px">Örnek/notlar</th>
</tr>



<tr>
<td>
<p>Aşağıdaki karakterlerden birini eklemek için, ters eğik çizgiyle birlikte ön ek koyun:</p>

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
<td>Özel karakter eklemeyle ilgili bazı örnekler
<p>\\ elde etmek için ```\\``` girin </p>
<p>_ elde etmek için ```\_``` girin </p>
<p>\# elde etmek için ```\#``` girin </p>
<p>\( elde etmek için ```\(``` girin </p>
<p>\. elde etmek için ```\.``` girin </p>
<p>\! elde etmek için ```\!``` girin </p>
</td>
</tr>

</tbody>
</table>