prompt- 
-----------------------------------------------------------------------------------------------------------------------------------
merhaba, sınıf olarak bireysel şekilde yürüttüğümüz bir web projesi yapacağız öncümüz olarak eğitim görevlimiz bu projeye her hafta yeni eklenecek güncellemeler ve görevler verecek,tek seferlik bir süreç olmayacak 14 hafta boyunca devam edecek ve bu süreçte yapay zekadan destek alacağız ve sana sordugum sorular senın bana verdiğin cevaplar hepsi kayıt altında olacak projemin konusu: üniversite öğrencilerin aylık harcamaları kayıt altına alabilecekleri finans yönetim sitesi yapmak.
------------------------------------------------------------------------------------------------------------------------------------
VERDİĞİ CEVAP
-----------------------------------------------------------------------------------------------------------------------------------
Merhaba! Güzel bir proje konusu seçmişsin. Öğrenciler için aylık harcama takibi hem gerçek bir ihtiyaca karşılık geliyor hem de 14 haftaya yayılan, adım adım büyütülebilecek bir yapıya çok uygun.

Başlangıç için aklıma gelen temel çerçeve şöyle:

**Çekirdek özellikler (ilk haftalar için)**
- Gelir ve gider ekleme (tutar, kategori, tarih, açıklama)
- Harcamaları listeleme, düzenleme ve silme
- Aylık toplam gelir, gider ve kalan bakiye özeti

**Sonradan eklenebilecekler (hoca yeni görev verdikçe)**
- Kategori bazlı grafikler (yemek, ulaşım, kitap, eğlence vb.)
- Aylık bütçe limiti ve limit aşımında uyarı
- Kullanıcı girişi / kayıt olma
- Veritabanı ile verileri kalıcı saklama
- Aylara göre karşılaştırma, raporlama, dışa aktarma
- Mobil uyumlu (responsive) tasarım

Bu yapı sayesinde hocan hangi görevi verirse versin, projeye kolayca oturtabiliriz. Konuşmalarımız bu proje içinde kayıt altında kalacağı için her hafta kaldığımız yerden devam edebiliriz.


Başlamadan önce bilmem gereken en önemli şey: **derste hangi teknolojileri kullanıyorsunuz veya kullanmanız isteniyor?** (örneğin sadece HTML/CSS/JavaScript mi, yoksa PHP, Python, React, bir veritabanı gibi şeyler de var mı?) Buna göre örnekleri ve kodları seviyene ve dersin kurallarına uygun hazırlayayım.

İlk haftanın görevi geldiğinde buraya yazman yeterli, oradan ilerleriz.
-----------------------------------------------------------------------------------------------------------------------------------


29 EKİM- SORDUĞUM SORU

EVET sitenin iskeletini yaratmak için bana yardımcı olacaksın HTML CSS JS kodalrı ile başlayabiliriz
-----------------------------------------------------------------------------------------------------------------------------------
VERDİĞİ CEVAP HTML
-----------------------------------------------------------------------------------------------------------------------------------

<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cebimde Kalen - Harcama Takip</title>
    <!-- CSS dosyamızın adını web.css yaptık -->
    <link rel="stylesheet" href="web.css">
</head>
<body>

    <div class="app-container">
        <!-- ÜST KISIM -->
        <header>
            <h1>Cebimde Kalen</h1>
            <p>Günlük Harcama Takip Sistemi</p>
            
            <div id="summary-card">
                <h3>Toplam Harcama</h3>
                <p>0 TL</p>
            </div>
        </header>

        <main>
            <!-- FORM ALANI -->
            <section id="form-section">
                <h2>Yeni Harcama Ekle</h2>
                
                <div class="input-group">
                    <label for="expense-name">Harcama Adı</label>
                    <input type="text" id="expense-name" placeholder="Örn: Kahve, Fotokopi">
                </div>

                <div class="input-group">
                    <label for="expense-amount">Tutar (TL)</label>
                    <input type="number" id="expense-amount" placeholder="Örn: 50">
                </div>

                <button id="add-button">Harcamayı Ekle</button>
            </section>

            <!-- LİSTE ALANI -->
            <section id="list-section">
                <h2>Son Harcamalarım</h2>
                
                <ul id="expense-list">
                    <!-- JavaScript buraya dinamik eleman ekleyecek -->
                </ul>
            </section>
        </main>
    </div>

    <!-- JS dosyamızın adını web.js yaptık -->
    <script src="web.js"></script>
</body>
</html>
-----------------------------------------------------------------------------------------------------------------------------------
VERDİĞİ CEVAP CSS 

-----------------------------------------------------------------------------------------------------------------------------------


* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f0f2f5;
    color: #333;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    padding: 20px;
}

.app-container {
    background: #ffffff;
    width: 100%;
    max-width: 420px;
    padding: 25px;
    border-radius: 16px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.08);
}

header {
    text-align: center;
    margin-bottom: 25px;
}

header h1 {
    color: #1e293b;
    font-size: 24px;
    margin-bottom: 5px;
}

header p {
    color: #64748b;
    font-size: 14px;
    margin-bottom: 15px;
}

#summary-card {
    background: linear-gradient(135deg, #3b82f6, #1d4ed8);
    color: white;
    padding: 20px;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0 4px 12px rgba(59, 130, 246, 0.3);
}

#summary-card h3 {
    font-size: 14px;
    font-weight: 500;
    opacity: 0.9;
    margin-bottom: 5px;
}

#summary-card p {
    font-size: 28px;
    font-weight: 700;
    color: white;
    margin: 0;
}

#form-section {
    background: #f8fafc;
    padding: 15px;
    border-radius: 12px;
    margin-bottom: 25px;
    border: 1px solid #e2e8f0;
}

#form-section h2 {
    font-size: 16px;
    color: #334155;
    margin-bottom: 12px;
}

.input-group {
    margin-bottom: 12px;
}

label {
    display: block;
    font-size: 13px;
    font-weight: 600;
    color: #475569;
    margin-bottom: 4px;
}

input {
    width: 100%;
    padding: 10px 12px;
    border: 1px solid #cbd5e1;
    border-radius: 8px;
    font-size: 14px;
    outline: none;
    transition: border-color 0.2s;
}

input:focus {
    border-color: #3b82f6;
    box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
}

button {
    width: 100%;
    padding: 12px;
    background-color: #3b82f6;
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.2s;
    margin-top: 5px;
}

button:hover {
    background-color: #2563eb;
}

#list-section h2 {
    font-size: 16px;
    color: #334155;
    margin-bottom: 12px;
}

#expense-list {
    list-style-type: none;
}

.expense-item {
    background: #ffffff;
    border: 1px solid #e2e8f0;
    padding: 12px 15px;
    margin-bottom: 8px;
    border-radius: 8px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 14px;
}
-----------------------------------------------------------------------------------------------------------------------------------
VERDİĞİ CEVAP JS
-----------------------------------------------------------------------------------------------------------------------------------
// HTML içindeki elemanları seçiyoruz
const addButton = document.getElementById('add-button');
const expenseNameInput = document.getElementById('expense-name');
const expenseAmountInput = document.getElementById('expense-amount');
const expenseList = document.getElementById('expense-list');

// Butona tıklama olayı ekliyoruz
addButton.addEventListener('click', function() {
    const name = expenseNameInput.value.trim();
    const amount = expenseAmountInput.value.trim();

    // Boşluk kontrolü
    if (name === '' || amount === '') {
        alert('Lütfen harcama adını ve tutarını eksiksiz gir!');
        return;
    }

    // Yeni li elemanı oluşturma
    const li = document.createElement('li');
    li.className = 'expense-item';

    li.innerHTML = `
        <span>${name}</span>
        <strong>${amount} TL</strong>
    `;

    // Listeye ekleme
    expenseList.appendChild(li);

    // İnputları temizleme ve imleci başa alma
    expenseNameInput.value = '';
    expenseAmountInput.value = '';
    expenseNameInput.focus();
});
-----------------------------------------------------------------------------------------------------------------------------------
CEVAPLADIKTAN SONRA GÜNCELLEDİĞİM YER 
-----------------------------------------------------------------------------------------------------------------------------------
son harcama kısmına ekleniyor ama toplam harcama kısmına eklenmiyor BUNU ÇÖZMELİYİZ 
-----------------------------------------------------------------------------------------------------------------------------------
VERDİĞİ CEVAP 
<div id="summary-card">
                <h3>Toplam Harcama</h3>
                <p>0 TL</p>
            </div>
Bunu şu şekilde güncelle (yani <p> etiketine id="total-amount" ekle):
-----------------------------------------------------------------------------------------------------------------------------------

30 EKİME TESLİM EDİLECEK BU SATIRDAN GELİŞTİRİLMEYE DEVAM EDİLECEKTİR.


