# ERP'ye "Gazete Atölyesi" sekmesi ekleme (site koduna erişmeden)

Bu klasördeki betik, radiotedu.com ERP sayfası açıldığında sidebar'a **📰 Gazete Atölyesi** sekmesini kendi tarayıcınızda ekler. Sekmeye tıklayınca Atölye, sidebar görünür kalacak şekilde sayfanın içinde açılır.

## Bir kerelik kurulum

1. **Tampermonkey eklentisini kurun.** Tarayıcınızın eklenti mağazasında "Tampermonkey" aratın (Chrome Web Store / Opera eklentileri / Edge eklentileri).
   - Chrome veya Edge kullanıyorsanız: eklentiler sayfasında (`chrome://extensions`) **Geliştirici modu** açık olmalı, Tampermonkey ayrıntılarında da **Kullanıcı betiklerine izin ver** seçeneği açılmalı.
2. Tampermonkey simgesi → **Yeni betik oluştur**. Açılan editördeki her şeyi silin.
3. `gazete-atolyesi.user.js` dosyasının **tüm içeriğini** kopyalayıp yapıştırın, **Ctrl + S** ile kaydedin.

## Her kullanımda

1. `Gazete Atolyesi Baslat.bat` dosyasına çift tıklayın. Açılan siyah pencere **açık kalsın** (simge durumuna küçültebilirsiniz).
2. radiotedu.com/erp sayfasını açın veya yenileyin. Sidebar'da **Avantajlar** altında **📰 Gazete Atölyesi** görünür.
3. Tarayıcı "yerel ağdaki cihazlara erişim" izni sorarsa **İzin ver** deyin; Atölye bilgisayarınızda çalıştığı için gereklidir.

Başlat dosyası editör klasörünü (`rtai-newspaper-editor-main`) bu klasörün bir ya da iki üstünde arar. Editör başka bir yerdeyse dosyayı Not Defteri ile açıp `set "ATOLYE_DIR="` satırına tam yolu yazın.

Başlat dosyası çalışmıyorsa sekme yine görünür ama "Gazete Atölyesi çalışmıyor" uyarısı gösterir; dosyayı çalıştırıp **Yeniden dene**'ye basın.

## Bilinmesi gerekenler

- Betik, Atölye'nin ince ve yuvarlak kaydırma çubuğu tasarımını Hub'daki **tüm** kaydırma çubuklarına (sidebar, tablolar, sonradan açılan pencereler dahil) uygular; çubuk Hub'ın açık/koyu moduna göre renk değiştirir. Betiği daha önce kurduysanız yeni sürümü (1.1.1) aynı şekilde yapıştırıp kaydedin.

- Sekme **yalnızca bu kurulumu yapan kişinin tarayıcısında** görünür. Diğer ekip üyeleri aynı adımları uygulamalıdır.
- Gazeteler tarayıcıda saklanır. ERP içinde açılan Atölye'nin kayıtları, Atölye'yi doğrudan `http://127.0.0.1:4173` adresinden açtığınızdaki kayıtlarla aynı değildir (tarayıcı güvenliği gereği ayrılır). Hep aynı yoldan açın; aktarmak için **Paketi indir / Dosyadan gazete ekle** kullanın.
- Site menüsünü büyük ölçüde değiştirirse betik sekmeyi bulamayabilir. Betiğin başındaki `ANCHOR_LABELS` listesine sidebar'daki başka bir menü adını yazmak genelde yeter.
- Kalıcı ve herkes için çalışan çözüm: Atölye'nin `dist/` klasörünü site sunucusuna (ör. `radiotedu.com/gazete/`) koyup sidebar'a site yöneticisinin bağlantı eklemesidir. O durumda betikteki `ATOLYE_URL` satırı yeni adresle değiştirilebilir veya betik kaldırılabilir.
