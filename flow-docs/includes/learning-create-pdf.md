Bu konu başlığında, Contoso Flooring’in belgeleri standart biçime dönüştürüp bulutta güvenli bir şekilde saklamak üzere SharePoint Online’da depolamak için Microsoft Flow’u nasıl kullandığını öğreneceksiniz. OneDrive İş klasörüne yeni bir dosya eklendiğini algılayan ve bu dosyayı PDF biçimine dönüştürüp bir SharePoint Online klasörüne depolayan bir akış oluşturacaksınız. 

## <a name="prerequisites"></a>Önkoşullar
Bu senaryo için, bir PDF dönüştürme hizmeti olan **Muhimbi**’ye sahip bir hesaba ihtiyacınız olacak. Zaten bir Muhimbi hesabınız yoksa, [ücretsiz 30 günlük deneme](http://www.muhimbi.com/Products/PDF-Converter-for-SharePoint/Products-PDF-Converter-for-SharePoint-Free-Trial.aspx) için kaydolabilirsiniz. Uygulamayı SharePoint Online siteniz üzerinden dağıtmak için bu sayfadaki yönergeleri izleyin. 

## <a name="create-the-source-and-target-folders"></a>Kaynak ve hedef klasörler oluşturma
Öncelikle OneDrive İş ve SharePoint Online üzerinde kaynak ve hedef klasörler oluşturmanız gerekir. 

1. OneDrive İş’te **Dosyalar** bölümünde **Tamamlanan Belgeler** adlı bir klasör oluşturun. 
   
    ![](./media/learning-create-pdf/onedrive-folder.png)
2. SharePoint Online’daki **Paylaşılan Belgeler** bölümünde, **PDF - Tamamlanan dosyalar** adlı bir klasör oluşturun. 
   
    ![](./media/learning-create-pdf/sharepoint-folder.png)

## <a name="create-the-flow"></a>Akışı oluşturma
1. Microsoft Flow’da **Akışlarım**’ı seçin ve **Boş akış oluştur**’u seçin. 
   
    ![](./media/learning-create-pdf/create-blank-flow.png)
2. **Yüzlerce bağlantı ve tetikleyiciyi arayın** seçeneğini belirleyin.
3. **OneDrive**’ı arayın, **OneDrive İş**’i seçin ve daha sonra **OneDrive İş - Bir dosya oluşturulduğunda** tetikleyicisini seçin. **Klasör** içinde, klasör simgesini ve önceki adımda oluşturduğunuz **Tamamlanan Belgeler** klasörünü seçin. 
   
    ![](./media/learning-create-pdf/onedrive-trigger.png)
4. **Yeni adım**'ı ve ardından **Eylem ekle**'yi seçin. 
   
    ![](./media/learning-create-pdf/new-action.png)
5. **Muhimbi**’yi arayın, **Muhimbi PDF** bağlayıcısını seçin ve **Muhimbi PDF - Belgeyi dönüştür** eylemini seçin.
   
    ![](./media/learning-create-pdf/muhimbi-action.png)
6. Bu noktada, Microsoft Flow tarafından Muhimbi için kimlik doğrulaması gerçekleştirmeniz istenebilir. Microsoft Flow’un Muhimbi hizmetini kullanması için **SharePoint kiracı kimliğinizi** kullanarak Muhimbi’yi kaydetmeniz gerekir. 
   
   1. Kiracı kimliğinizi bulmak için, SharePoint Online’da **Ayarlar** dişli simgesini seçin ve **Site ayarları**’nı seçin.
   2. **Site Koleksiyonu Yönetimi** bölümünde **Site koleksiyonu uygulama izinleri**’ni seçin. Kiracı kimliğiniz uygulama listelerinde “**@**” sembolünden sonra gelen tanımlayıcıdır. 
      
       ![](./media/learning-create-pdf/tenant-id.png)
7. **Belge dönüştürme** eyleminde, aşağıdaki değerleri ayarlayın:
   
   * **Kaynak dosya adı**: Dinamik içerik listesinden **Dosya adı**’nı seçin.
   * **Kaynak dosya içeriği**: Dinamik içerik listesinden **Dosya içeriği**’ni seçin.
   * **Çıkış biçimi**: Açılır listeden **PDF**’yi seçin.
     
     ![](./media/learning-create-pdf/muhimbi-configuration.png)

Şu ana kadar akışınızı aşağıdaki adımlarla yapılandırdınız: 

1. Belirli bir OneDrive İş klasörüne yeni bir dosya eklendiğinde akış tetiklenir 
2. Muhimbi hizmeti bu dosyayı PDF’ye dönüştürür. 

Son adım için, PDF belgesini ekibin erişebileceği bir SharePoint Online klasörüne taşıyan bir eylem ekleyeceksiniz.  

1. **Yeni adım**'ı ve ardından **Eylem ekle**'yi seçin.  **SharePoint**’i arayın ve **SharePoint - Dosya oluşturma** eylemini seçin. 
   
    ![](./media/learning-create-pdf/sharepoint-create-file.png)
2. **Dosya oluşturma** eyleminde aşağıdaki değerleri ayarlayın:
   
   * **Site adresi**: SharePoint sitenizin URL’si.  
   * **Klasör yolu**: Klasör simgesini seçip **PDF - Tamamlanan dosyalar** klasörüne gidin.
   * **Dosya adı**: **Belge dönüştürme** için dinamik içerik listesinden, **Temel dosya adı**’nı seçip dosya uzantısıyla SharePoint’e kaydetmek için “**.pdf**” ekleyin. 
   * **Dosya içeriği**: **Belge dönüştürme** için dinamik içerik listesinden **İşlenen dosya içeriği**’ni seçin.
3. Çalışmanızı kaydetmek için sayfanın en üstünde **Akış oluştur**’u seçin.
   
    ![](./media/learning-create-pdf/sharepoint-configure-file.png)

## <a name="test-the-flow"></a>Akışı test etme
1. Akışı test etmek için, OneDrive İş’teki **Tamamlanan Belgeler** klasörünüze yeni bir dosya ekleyin. 
2. Flow’da **Akışlarım**’ı seçip çalıştırma geçmişini görüntülemek için yeni akışı seçin. Varsayılan olarak, akış beş dakikada bir çalıştırılacak biçimde yapılandırılmıştır. 
3. Akış çalıştırıldıktan sonra, dosyanın PDF’ye dönüştürüldüğünü ve SharePoint **PDF - Tamamlanan dosyalar** klasörüne kaydedildiğini doğrulayın. 
   
    ![](./media/learning-create-pdf/test-the-flow.png)

