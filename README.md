# Dilekçe Atıf Denetçisi

**Türkçe Emsal Karar Atıflarında Destekleme Doğruluğu: Uzman Etiketli Veri Seti ve Kanıta Dayalı Seçici Doğrulama**

Bitirme Projesi ve TÜBİTAK 2209-A önerisi · Umut Şahin · Bilişim Sistemleri Mühendisliği, Kocaeli Üniversitesi

📄 **Revize proje önerisi (2 Kasım 2026):** [Revize_Proje_Onerisi_2_Kasim_2026.pdf](Revize_Proje_Onerisi_2_Kasim_2026.pdf)

---

## Problem

Dilekçelerde atıf yapılan bir emsal kararın var olması yetmez; kararın, dilekçedeki iddiayı gerçekten desteklemesi gerekir. Yapay zekâ destekli hukuk araçları yaygınlaştıkça hem var olmayan kararlara hem de iddiayı desteklemeyen gerçek kararlara atıf yapılması riski artmaktadır.

Türkiye'de içtihat araması ve dilekçe taslağı üreten ticari araçlar bulunmaktadır. Ancak bu araçların, atıf yapılan kararın iddiayı destekleyip desteklemediğini ne sıklıkla doğru belirlediği bağımsız ve tekrarlanabilir bir test setiyle ölçülmemiştir.

## Projenin yaklaşımı

Bu proje bir atıf denetleme aracı geliştirmekten çok, bu denetimin Türkçede **ne kadar güvenilir yapılabildiğini ölçen** bir araştırmadır.

Atıf kontrolünde iki ayrı soru vardır:

| Soru | Durum |
|---|---|
| Karar var mı? (künye doğrulama) | Türkçede açık bir benchmark ile ölçülmektedir (Legaluga Law Benchmark) |
| Karar iddiayı destekliyor mu? | **Bu projenin konusu.** Türkçede ölçülmemiştir |

## Özgün katkılar

1. **Türkçe iddia–karar test seti (ana çıktı):** İş hukuku Yargıtay kararları üzerinde *destekliyor / çelişiyor / yetersiz kanıt* olarak etiketlenmiş iddia–karar çiftleri. Test seti hukuk uzmanı onaylıdır.
2. **İlk karşılaştırmalı ölçüm:** Benzerlik, BERT/NLI ve LLM tabanlı yaklaşımların bu sette ne sıklıkla yanlış destekleme yaptığının hata türlerine göre ölçülmesi.
3. **Kanıta Dayalı Seçici Doğrulama (KSD):** Modelin gösterdiği kanıt alıntısını karar metninde birebir arayan, güveni eşik değerin altındaysa karar vermeyip atfı uzmana yönlendiren doğrulama mekanizması.

## Kapsam

- Yargıtay'ın iş uyuşmazlıklarına bakan dairelerinin UYAP Emsal'de yayımlanmış kararları
- Tek bir iddia ile tek bir karar arasındaki destek ilişkisi
- Kapsam dışı: diğer hukuk alanları, kararın güncelliği (HGK/İBK), ticari ürünlerin doğrudan test edilmesi

## Veri seti ve ölçüm

| | Hedef |
|---|---|
| İddia–karar çifti | ~1.500 |
| Uzman onaylı test seti | 300 örnek |
| Etiketleyiciler arası uyum | Cohen's kappa ≥ 0,70 |
| Karşılaştırılan yöntemler | Benzerlik, BERT/NLI, LLM, en iyisi + KSD |

**Ana metrik: Yanlış Destekleme Oranı (YDO).** Gerçek etiketi *çelişiyor* veya *yetersiz kanıt* olan örneklerden *destekliyor* olarak tahmin edilenlerin oranı. Hedef: KSD ile en az %30 göreli azalma, Macro-F1 kaybı en fazla 2 puan. Hedefler ön hedeftir; pilot sonuçlarına göre kesinleşecektir.

## İş paketleri (12 ay)

| İP | İçerik | Ay |
|---|---|---|
| İP1 | Literatür araştırması ve kaynak doğrulama | 1–2 |
| İP2 | Veri erişimi ve pilot çalışma | 1–3 |
| İP3 | Veri seti oluşturma ve etiketleme | 3–6 |
| İP4 | Yöntem geliştirme (işlem hattı + KSD) | 5–8 |
| İP5 | Karşılaştırmalı deneyler | 8–10 |
| İP6 | Prototip ve raporlama | 10–12 |

## Durum

Proje öneri aşamasındadır. Ayrıntılar, literatür karşılaştırması, ticari ürün taraması ve kaynakça için [revize proje önerisine](Revize_Proje_Onerisi_2_Kasim_2026.pdf) bakınız.
