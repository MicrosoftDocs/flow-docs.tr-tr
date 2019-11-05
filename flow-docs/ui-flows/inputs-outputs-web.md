---
title: Web UI akışlarında giriş ve çıkışları kullanma | Microsoft Docs
description: Web UI akışlarında girişleri ve çıkışları kullanın.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8506846f8081819ad42c70e820397bdc43536e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549358"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Web UI akışlarında girişleri ve çıkışları kullanma

[Bu konu ön sürüm belgesidir ve değişikliğe tabidir.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs-for-a-web-ui-flow"></a>Bir Web Kullanıcı arabirimi akışı için girdileri tanımlama

UI akışının girişleri, bir veritabanı veya başka bir kullanıcı arabirimi akışı gibi bir dış kaynaktan, otomatikleştirebileceğiniz hedef eski yazılımlara bilgi geçirmenize olanak sağlar.

Başlatmadan önce kullanılan (genellikle **Mağaza** komutları aracılığıyla yapılan) herhangi bir değişken otomatik olarak bir giriş değişkeni olarak kabul edilir ve **Web için bir kullanıcı arabirimi akışı Çalıştır** eylem kartında görüntülenir.

Dize ilişkilendirme aracılığıyla değişkenleri kullanabilirsiniz. Örneğin, Click komutunun hedef alanını "ID =\${ElementID}" olarak değiştirebilirsiniz. Ya da Type komutunun Value alanını "\${InputText}" olarak değiştirin.

Komut, **pencere boyutunu ayarla** ve aşağıdaki ekran görüntülerinde komut **türü** başlatılmamış değişkenleri \${Width}, \${Height} ve \${Search} kullanın. Bu değişkenler giriş değerlerine dönüşecek.

![Pencere boyutunu ve türünü ayarla](../media/inputs-outputs-web/f05cb445dad212aaf395b66ba969622c.png "Pencere boyutunu ve türünü ayarla")

Değişkenleri doğrudan bazı komutlarda kullanabilirsiniz; Örneğin, forEach komutunun target/value alanları her iki değişkendir, "\${}" ile çevrelemek zorunda kalmazsınız.

Değişken adı doğrudan hangi komutların olacağını öğrenmek için lütfen [Selenium komutları](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) başvurusuna başvurun.

## <a name="define-outputs-for-a-web-ui-flow"></a>Web Kullanıcı arabirimi akışı için çıktıları tanımlama

Selenium betikte tanımlanan herhangi bir değişken otomatik olarak bir çıkış değeri olur. Değişkenleri bildirmek için aşağıdaki komutları kullanın:

[Saklayabilir](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[Depo özniteliği](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[JSON depola](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[Mağaza başlığı](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[Mağaza değeri](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[Mağaza pencere tutamacı](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[Mağaza XPath sayısı](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

Betiği [Yürüt](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script)(komut dosyasının sonunda depolamak istediğiniz nesneyi döndürmek için ' Return ' sözdizimini ekleyin)

## <a name="next-steps"></a>Sonraki adımlar

- [Web UI akışları oluşturmayı](create-web.md)öğrenin.
- [UI akışlarını nasıl tetikleyeceğinizi](run-ui-flow.md)öğrenin.

