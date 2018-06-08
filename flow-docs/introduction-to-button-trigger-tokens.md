---
title: Düğme tetikleyici belirteçlerine giriş | Microsoft Docs
description: Microsoft düğme akışları için düğme tetikleyici belirteçleri tanıtımı.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/12/2016
ms.author: deonhe
ms.openlocfilehash: c3231811e5318b1fe941e005012c2890c83f6e76
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34308775"
---
# <a name="get-started-with-button-trigger-tokens"></a>Düğme tetikleyici belirteçleri kullanmaya başlayın.
## <a name="what-are-button-trigger-tokens"></a>Düğme tetikleyici belirteçler nedir?
Düğme tetikleyici belirteçler, üzerinde bir [düğme akışı](introduction-to-button-flows.md) çalışan cihaz tarafından bilinen ve kullanılabilen veri noktalarıdır. Bu belirteçler, geçerli saat veya cihazın belirli bir andaki coğrafi konumu gibi faktörlere bağlı olarak değişiklik gösterir.  

Örneğin bir akıllı telefonda düğme akışı çalıştırıyorsanız telefonunuzun bulunduğunuz konumdaki **saatin** yanı sıra tarihi ve geçerli adresinizi de biliyor olma olasılığı yüksektir. Bu bağlamda saat, tarih ve telefonun bulunduğu adres değerlerinin tamamı düğme akışının çalıştırıldığı zamana göre belirlenir. Bunlar, cihazda yürütülen herhangi bir düğme akışında otomatik olarak sağlanır. Bu tetikleyici belirteçleri kullanarak birine konumunuzu sağlama veya belirli bir iş/hizmet aramasına ne kadar zaman harcadığınızı izleme gibi yinelemeli görevleri olabildiğince azaltan kullanışlı akışlar oluşturabilirsiniz.

### <a name="list-of-button-trigger-tokens"></a>Düğme tetikleyici belirteçlerin listesi
Düğme akışlarınızı oluştururken kullanabileceğiniz düğme tetikleyici belirteçlerin listesi aşağıda verilmiştir.

| Parametre | Açıklama |
| --- | --- |
| Şehir |Akışı çalıştıran cihazın bulunduğu şehir. |
| Ülke/Bölge |Akışı çalıştıran cihazın bulunduğu ülke/bölge. |
| Tam adres |Akışı çalıştıran cihazın tam adresi. |
| Enlem |Akışı çalıştıran cihazın bulunduğu enlem. |
| Boylam |Akışı çalıştıran cihazın bulunduğu boylam. |
| Posta Kodu |Akışı çalıştıran cihazın bulunduğu konumun posta kodu. |
| Eyalet |Akışı çalıştıran cihazın bulunduğu eyalet. |
| Sokak |Akışı çalıştıran cihazın bulunduğu sokak. |
| Zaman Damgası |Akışı çalıştıran cihazın bulunduğu bölgedeki saat. |
| Tarih |Akışı çalıştıran cihazın bulunduğu bölgedeki tarih. |
| Kullanıcı adı |Akışı çalıştıran cihazda oturum açan kişinin kullanıcı adı. |
| Kullanıcı e-postası |Akışı çalıştıran cihazda oturum açan kişinin e-posta adresi. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Tetikleyici belirteçleri kullanan bir düğme akışı oluşturma
Düğme oluştururken tetikleyici belirteçleri kullanarak düğmenize zengin işlevler ekleyebilirsiniz.

Bu adım adım kılavuzda, bir Android cihazda düğme akışı oluşturacağız. Düğme akışı, yöneticinize göndereceğiniz bir "**Evden çalışıyorum**" e-postasında tarihi ve tam adresinizi göndermeye yönelik tetikleyici belirteçler kullanacak.

Bu adım adım kılavuzdaki ekran görüntüleri bir Android cihazdan alınmıştır, ancak iOS ve Windows Phone cihazlarda da benzer işlemler uygulanır.

### <a name="prerequisites"></a>Önkoşullar
* Microsoft Flow’a erişimi olan bir iş veya okul e-posta adresi ya da [Microsoft Hesabı](https://account.microsoft.com/about?refd=www.microsoft.com).
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulaması.

Haydi başlayalım:

1. Flow’u başlatın ve **Gözat** ’ı seçin  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/1.png)  
2. **Düğme** kategorisinden **Yöneticinize 'Bugün evden çalışıyorum' e-postası gönderin** seçeneğini belirleyin   
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/2.png)  
3. **BU ŞABLONU KULLAN**’ı seçin  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/3.png)  
4. **E-posta gönder** kartında **Düzenle**’yi seçin  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. **Konu** metin kutusuna dokunun ve metin kutusuna "WFH" ifadesinden sonra şu metni girin: " **bugün -**". Metin kutusuna dokunduğunuzda bir parametre/belirteç listesinin de açıldığını fark edeceksiniz. Bir sonraki adımda e-postanın konusuna tarihi eklemek için bu belirteçlerden birini kullanacağız.  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/4.png)  
6. İmleç, konu metin kutusundayken ekranı kaydırarak **el ile** parametre listesine gidin ve **Tarih**’e dokunun. Veri parametresinin artık **Konu** metin kutusunda olduğunu görebilirsiniz:  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/6.png)  
7. Sayfayı kaydırarak **Gövde** metin kutusuna gidin ve varsayılan iletiden sonra ek belirteçler eklenebilmesi için buraya dokunun.  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/7.png)  
8. **Tam adres** parametresine ve ardından **Oluştur**’a dokunun  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/8.png)  
9. **Bitti**’ye dokunun. Düğme akışınız oluşturuldu.  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>Düğme akışını çalıştırma
**NOT**: Bu düğme akışı, konumunuzu e-posta yoluyla gönderir.  

1. Ekranın en altındaki **Düğmeler** kategorisine dokunun. Kullanma izninizin olduğu düğmelerin listesini görürsünüz. Az önce oluşturduğunuz düğme akışını temsil eden düğmeye dokunun:  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/10.png)  
2. Düğme akışının cihazınızın konum bilgilerine erişmesine izin verdiğinizi belirtmek için **İZİN VER**’e dokunun.  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/11.png)  
3. Birkaç saniye içinde e-postanın yöneticinize gönderildiğini fark edeceksiniz:  
   ![düğme tetikleyici belirteç](./media/introduction-to-button-trigger-tokens/12.png)  

Tebrikler, hem tarih hem de tam adres tetikleyici belirteçleri kullanan bir düğme akışı oluşturdunuz. 

## <a name="next-steps"></a>Sonraki adımlar
* [Düğme akışları paylaşma](share-buttons.md)
* [Düğme akışları hakkında bilgi edinin](introduction-to-button-flows.md)  
* [Akışlar hakkında bilgi edinin](guided-learning/get-started.yml?tutorial-step=1)

