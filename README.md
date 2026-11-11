# 🛒 Olist E-Commerce Data Analysis (Python)

Bu proje, Brezilya'nın en büyük e-ticaret platformlarından biri olan Olist veri seti kullanılarak hazırlanmış kapsamlı bir Python veri analizi çalışmasıdır.

Amaç; sipariş davranışlarını, fiyat dağılımlarını, teslimat sürelerini, müşteri memnuniyetini ve ödeme yöntemlerinin tamamlanma oranlarını analiz etmektir.

## 🛠️ Tools & Technologies

- Python (Google Colab)
- Pandas · NumPy
- Plotly Express
- Matplotlib · Seaborn
- SciPy (Chi-Square Test)
- EDA + Feature Engineering

## 📥 1. Data Loading & Preparation

Projede kullanılan veri setleri:

- `olist_orders_dataset.csv`
- `olist_order_items_dataset.csv`
- `olist_products_dataset.csv`
- `olist_customers_dataset.csv`
- `olist_sellers_dataset.csv`
- `olist_order_payments_dataset.csv`
- `olist_order_reviews_dataset.csv`

Notebook’ta ilk olarak tüm CSV dosyaları pandas DataFrame olarak yüklendi, gerekli kolon seçimi ve temizliği yapıldı.

## 🔍 2. Exploratory Data Analysis (EDA)

Analiz kapsamında yapılan temel incelemeler:

**✔️ Sipariş fiyatı istatistikleri**

- Ortalama ürün fiyatı
- Order bazında toplam sepet tutarı
- En yüksek ve en düşük fiyatlı ürünler
- Kategori bazında fiyat karşılaştırmaları

**✔️ Ürün kategorisi analizleri**

- En çok sipariş edilen kategoriler
- En yüksek gelir getiren kategoriler
- “Informática Acessórios” gibi kategorilerin fiyat davranışları

**✔️ Teslimat süresi analizi**

- `order_purchase_timestamp` → `order_delivered_customer_date` farkı
- Ortalama teslim süresi
- Geciken teslimatların oranı
- Gecikmenin yorum puanlarına etkisi

## 📊 3. Visualizations

Notebook’ta aşağıdaki grafikler oluşturulmuştur:

- Toplam sepet tutarı dağılımı
- Kategori bazında ortalama fiyat grafiği
- Teslim süreleri dağılım grafiği
- Ürün kategorisi popülerliği
- İnceleme puanı dağılımı
- Ödeme yöntemi tamamlanma oranları çubuğu

Tüm grafikler Plotly Express veya Matplotlib ile oluşturulmuştur.

## 📈 4. Statistical Test — Chi-Square Hypothesis Test

Analiz edilen hipotez:

**H0:** Ödeme yöntemi, siparişin tamamlanma oranını etkilemez
**H1:** Ödeme yöntemi, tamamlanma oranını etkiler

Notebook’ta:

- Ödeme yöntemi × sipariş tamamlanma durumu için contingency table oluşturuldu
- SciPy ile chi-square testi uygulandı
- Sonuç → p < 0.05 bulundu

➡️ Ödeme yönteminin siparişin iptal edilip edilmemesi üzerinde anlamlı etkisi vardır.
Kredi kartı en güvenilir yöntemdir; alternatif yöntemlerde iptal oranları daha yüksektir.

## 💡 5. Key Insights

- ⚠️ Teslim süresi uzadıkça review score düşüyor
- 💳 Kredi kartı siparişleri en yüksek tamamlanma oranına sahip
- ⏳ Geciken teslimatlar memnuniyeti ciddi şekilde etkiliyor
- 💸 Bazı kategoriler (ör. “Informática Acessórios”) daha yüksek fiyat ortalamasına sahip
- 📦 En yoğun kategori grupları en yüksek gelirleri getiriyor

## 📝 6. Analiz Bulgularının Özeti

**Teslimat Süresi & Müşteri Memnuniyeti:** Teslimat süresi ile müşteri memnuniyeti (yorum puanı) arasında istatistiksel olarak anlamlı, negatif yönlü bir ilişki tespit edilmiştir. Siparişlerin teslim süresi uzadıkça müşteri memnuniyet puanının belirgin bir şekilde düştüğü kanıtlanmıştır. Zamanında ve hızlı teslimat, müşteri sadakatini ve yüksek puanlamayı doğrudan etkileyen en kritik faktörlerdendir.

**Ürün Kategorileri & Sipariş Değerleri (Fiyat):** Seçilen en popüler ürün kategorilerinin ortalama fiyat düzeyleri arasında anlamlı farklar gözlemlenmiştir. Bu durum, farklı ürün gruplarının gelir katkısının ve müşteri segmentasyonunun homojen olmadığını, kategori bazlı özelleştirilmiş fiyatlandırma ve pazarlama stratejilerine ihtiyaç olduğunu ortaya koymaktadır.

**Ödeme Yöntemleri & Sipariş Tutarı:** Kredi kartı ile yapılan alışverişlerin ortalama tutarının, Boleto yöntemine kıyasla istatistiksel olarak anlamlı derecede daha yüksek olduğu belirlenmiştir. Kredi kartının sunduğu taksitlendirme imkanlarının, müşterileri daha yüksek bütçeli siparişler vermeye teşvik ettiği söylenebilir.

## 🧠 7. Business Recommendations

- Lojistik zinciri iyileştirilerek gecikme oranları azaltılmalı
- Yüksek değerli kategorilere stok & kampanya yatırımı yapılmalı
- Ödeme yöntemi seçim ekranlarında kredi kartı önerisi yapılabilir
- Gecikme riskinin yüksek olduğu bölgeler için ayrı SLA tanımlanabilir
- Müşteri deneyimi yönetimi için review score analizi düzenli yapılmalı

## ⚠️ 8. Analiz Kısıtlamaları (Limitations)

- **Zaman Serisi Dinamikleri:** Analizde mevsimsellik etkileri, özel indirim dönemleri (Black Friday vb.) ve makroekonomik faktörlerin zaman içindeki değişimleri tam olarak izole edilmemiştir.
- **Veri Eksiklikleri:** Bazı yorum mesajlarının ve ürün kategorisi detaylarının eksik olması dolayısıyla veri temizleme aşamasında dolgular yapılmıştır. Bu durum bazı kategorik dağılımları az da olsa etkilemiş olabilir.
- **Lojistik Detayları:** Teslimat sürelerinde satıcı ile kargo firmasının performansı net olarak ayrıştırılamamıştır.

## 🔭 9. İleri Analiz Önerileri & Sonraki Adımlar

- **Makine Öğrenmesi ile Müşteri Kaybı (Churn) Tahmini:** Teslimat gecikmelerinin ve düşük yorum puanlarının müşteri kaybı üzerindeki etkilerini tahmin eden sınıflandırma modelleri geliştirilebilir.
- **Kategori Bazlı Taksit Kampanyaları:** Kredi kartı kullanımının yüksek sepet tutarı getirmesi avantajını kullanarak, ortalama ürün fiyatı yüksek olan kategorilerde cazip taksit kampanyaları planlanabilir.
- **Lojistik ve Dağıtım Merkezlerinin Optimizasyonu:** Teslimat sürelerini 7 günün altına indirmek adına satıcıların ve ana dağıtım depolarının konum analizi yapılarak lojistik rotalar optimize edilmelidir.
