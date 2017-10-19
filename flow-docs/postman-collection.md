---
title: "Postman ile özel bir bağlayıcıyı açıklama | Microsoft Docs"
description: "Özel bağlayıcıları kaydetmek için Postman Collection oluşturma"
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/28/2017
ms.author: sunayv
ms.openlocfilehash: fe98999ea307367c7f3b032974fef9be6ca3f388
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="describe-a-custom-connector-with-postman"></a>Özel bağlayıcıyı Postman ile açıklama
[Postman](https://www.getpostman.com/), API geliştirme çalışmanızı hızlandırmaya ve kolaylaştırmaya yönelik bir araçtır. Bu öğreticide Postman Collection dosyasının nasıl oluşturulduğu gösterilir. Daha sonra bunu kullanarak Microsoft Flow’da kolayca [özel bağlayıcılar](register-custom-api.md) oluşturabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar
* [Postman uygulamasını](https://www.getpostman.com/apps) yükleyin.

## <a name="create-a-postman-collection"></a>Postman Collection oluşturma
Şimdi Azure Bilişsel Hizmetler [Metin Analizi API’si](https://www.microsoft.com/cognitive-services/text-analytics-api) için bir Postman Collection oluşturalım. Bu API, kendisine geçirdiğiniz dili, duyguyu ve önemli tümcecikleri tanımlar.

1. Postman Collection oluşturma işleminin ilk adımı bir istek oluşturmaktır. İstek oluştururken, HTTP fiilini, istek URL’sini, sorgu veya yol parametrelerini, üst bilgileri ve gövdeyi ayarlayabilirsiniz. Daha fazla bilgi için Postman belgelerinde [İstekleri Gönderme](https://www.getpostman.com/docs/requests) konusuna bakın. Dil Algılama API’si uç noktası için değerleri aşağıda gösterildiği gibi ayarlayın:
   
    ![Postman isteği](./media/postman-collection/request.png)
   
    Kullanılan parametre ve değerlerin ayrıntıları:
   
   | Parametre | Değer |
   | --- | --- |
   | Fiil |POST |
   | İstek URL’si |https://westus.api.cognitive.microsoft.com/text/analytics/v2.0/languages |
   | Params |numberOfLanguagesToDetect |
   | Yetkilendirme |“No Auth” |
   | Üst Bilgiler |Ocp-Apim-Subscription-Key = <your subscription key> <br/>Content-Type = application/json |
   | Gövde |<code>{<br/>&nbsp;&nbsp;&nbsp;"documents": [<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": "1",<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"text": "Hello World"<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;]<br/>}<code> |
2. İstekte bulunmak ve yanıt almak için **Gönder**’e tıklayın.
3. İsteği Postman Collection’a kaydetmek için **Kaydet**’e tıklayın.
   
    ![Postman yanıtı](./media/postman-collection/request-response-save.png)
4. **İsteği Kaydet** iletişim kutusunda **İstek adı** ve **İstek açıklaması** sağlayın. Bu değerleri özel bağlayıcınızda kullanacaksınız.
   
    ![Postman Collection’ı Kaydetme](./media/postman-collection/save-request-note.png)
   
    İsteğin yanıtını da kaydedebilirsiniz. Özel bağlayıcılar şu anda istek başına yalnızca bir yanıtı desteklemektedir. İstek başına birden çok yanıt kaydederseniz, yalnızca ilki kullanılır.
   
    ![Postman Yanıtı Kaydetme](./media/postman-collection/save-response.png)
5. Başka istekler ve yanıtlar oluşturarak ve kaydederek Postman Collection’ınızı oluşturmaya devam edin.
6. Tüm istekleriniz ve yanıtlarınız için Postman Collection oluşturmayı tamamladığınızda, koleksiyonu dışarı aktarın.
   
    ![Postman Dışarı Aktarma](./media/postman-collection/export.png)
7. Dışarı aktarma biçimi olarak **Collection v1**’i seçin.
   
    ![Postman Dışarı Aktarma](./media/postman-collection/export2.png)

Şimdi bu Postman Collection’ı kullanarak Microsoft Flow’da özel bağlayıcı oluşturabilirsiniz.

> [!IMPORTANT]
> Bir Postman koleksiyonundan özel bağlayıcı oluştururken, Microsoft Flow tarafından otomatik olarak eklenecek olan `Content-type` üst bilgisini eylemler ve tetikleyicilerden kaldırmayı unutmayın. **Güvenlik** bölümünde tanımlanmış olan kimlik doğrulama üst bilgileri (örneğin `Ocp-Apim-Subscription-Key`), eylemler ve tetikleyicilerden kaldırılmalıdır. 
> 
> 

Daha fazla bilgi için bkz. [Microsoft Flow’da özel bağlayıcılar kaydetme ve kullanma](register-custom-api.md).

