---
ms.openlocfilehash: 0e46ba9a9ff1044e72b8550b47d126e2999cfb71
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461121"
---
## <a name="what-is-an-environment"></a>Ortam nedir?
Ortam, Common Data Service üzerinde uygulamalar, akışlar ve iş verileri depolamak, yönetmek ve paylaşmak için kullanılan sanal bir alandır. Ortamlar coğrafi olarak konumlandırıldığından bir ortamın veritabanında depolanan tüm uygulama ve veriler de coğrafi olarak konumlandırılır.  

## <a name="terms-you-should-get-familiar-with"></a>Bilmeniz gereken terimler:

| **Terim** | **Açıklama** |
| --- | --- |
| **Yönetim merkezi** |Yönetim merkezi tüm ortamlarınızı ve veri kaybı önleme ilkelerini yönetmek için kullanılan [Web portalıdır](https://admin.flow.microsoft.com). |
| **Common Data Service** |Common Data Service, uygulamalarınıza veri depolama ve modelleme özellikleri eklemenize olanak sağlar. |
| **Ortam rolleri** |İki ortam rolü bulunur: Ortam Yöneticisi ve Ortam Oluşturucusu. |
| **Kullanıcı rolleri** |İki varsayılan kullanıcı rolü bulunur: Kuruluş Kullanıcısı ve Veritabanı Sahibi. Roller ekleyebilir ve izinleri bu rollerle ilişkilendirebilirsiniz. |

## <a name="purposes-for-an-environment"></a>Ortamın amaçları
Ortamları aşağıdakiler için kullanabilirsiniz:  

* Uygulamalar, akışlar ve iş verilerini farklı roller, güvenlik gereksinimleri veya kullanıcılara göre ayırın.  
* Uygulamalar, akışlar ve iş verilerini ekip veya departmanlarınızın konumuna göre ayırmak.
* Test ve üretim ortamlarını yönetmek.  

## <a name="how-to-use-environments"></a>Ortamları kullanma
Ortamlar kuruluşunuzun ihtiyaçlarına göre farklı amaçlarla kullanılabilir. Örneğin:  

* Tüm uygulama ve akışlarınızı tek bir ortamda oluşturmayı seçebilirsiniz 
* Farklı uygulama ve akış türleri için bir ortam oluşturmayı seçebilirsiniz. Örneğin, test ive üretim için ayrı ortamlar oluşturabilirsiniz.  
* Kuruluş yapınıza ve hatta ekip ve departmanlarınızın coğrafi konumlarına göre ortamlar oluşturmayı da seçebilirsiniz. Örneğin, Avustralya, Meksika ve Avrupa’da ekipleriniz varsa bu konumların her biri için bir ortam oluşturabilir ve bunları birbirinden bağımsız olarak yönetebilirsiniz.  

**Not**: Ortamlar kullanıcılar için görünür değildir, bu nedenle kullanıcıların hangi ortamlarda oldukları konusunda endişe duymaları gerekmez. Ortamlar, yöneticilerin kurumsal uygulamaları ve akışları kategorize etmek, yönetmek ve paylaşmak için kullanabileceği araçlardır.  

## <a name="what-are-roles"></a>Roller nedir?
Bir ortama erişimi olan bir kişiye **Ortam Yöneticisi** veya **Ortam Oluşturucusu** rolünün atanmış olması gerekir. Ortam yöneticileri, bir ortam üzerinde tüm yönetim görevlerini gerçekleştirebilir. Ortam oluşturucuları, mevcut bir ortamda kaynaklar oluşturabilir. Bir kişi aynı anda iki role de sahip olabilir.  

**Not**: Her kullanıcıya Microsoft Flow erişimi verildiğinde tüm kullanıcılar varsayılan bir ortama erişebilir. Kullanıcılar birden çok ortama erişebilir.  

## <a name="create-an-environment"></a>Ortam oluşturma
Ortamları [Microsoft Flow yönetim merkezinden](https://admin.flow.microsoft.com) bu adımları izleyerek oluşturabilirsiniz:  

1. Ortamınızı adlandırın.
2. Ortamınızın barındırılacağı bir bölge seçin.
3. İsteğe bağlı olarak ortamınız için bir veritabanı oluşturabilirsiniz. İsterseniz ortamı oluşturduktan sonra bir veritabanı oluşturabilirsiniz.
4. İsteğe bağlı olarak kimlerin veritabanına erişebileceğini seçin. Erişimi kısıtlayabilir veya herkese veritabanına erişim izni verebilirsiniz. 

## <a name="add-users-to-an-environment"></a>Kullanıcıları ortama ekleme
Bir ortam oluşturduktan sonra kullanıcıları Ortam Yöneticisi rolüne veya Ortam Oluşturucusu rolüne ekleyebilirsiniz. Diğer tüm yönetim görevleri gibi bu görevi de yönetim merkezinden gerçekleştirirsiniz.  

Ortam oluşturup kullanıcıları ekledikten sonra, iş verilerinizin kullanımını yönetmeye yardımcı olmak için bir veri kaybı önleme (DLP) ilkesi oluşturmak da isteyebilirsiniz. Bunu bir sonraki konuda ele alacağız. 

