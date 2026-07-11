# LEGIVRA AI ⚖️📄
> **"Evraklardan Kararlara"** - Kamu Evrak ve Yazışma Süreçleri İçin Akıllı Agent Destek Sistemi

LEGIVRA AI, çok ajanlı yapay zekâ (Multi-Agent AI) mimarisiyle kamu kurumlarındaki evrak işleme, mevzuat eşleştirme ve resmî yazışma süreçlerini dijitalleştiren yenilikçi bir **GovTech** platformudur. **TEKNOFEST 2026 Yapay Zekâ Dil Ajanları Yarışması** kapsamında geliştirilen projenin pilot kurumu **T.C. Tarım ve Orman Bakanlığı**'dır.

---

## 👥 Takım Hikâyesi ve Rol Dağılımı

LEGIVRA AI fikri, TEKNOFEST'in belirlediği *"Kamu Evrak ve Yazışma Süreçleri için Akıllı Agent Destek Sistemi"* probleminden doğmuştur. Kamu kurumlarında yürütülen evrak süreçlerinin zaman alıcı ve manuel yapısını analiz ederek, bu süreçleri yapay zekâ destekli çok ajanlı bir sistemle iyileştirebileceğimizi gördük. Farklı mühendislik disiplinlerinden gelen bilgi birikimimizi bir araya getirerek Tarım ve Orman Bakanlığı başta olmak üzere kamu kurumlarına uyarlanabilecek modüler ve sürdürülebilir bir karar destek platformu geliştirmeye başladık.

**Ortak hedefimiz;** kamu hizmetlerinde verimliliği artıran, karar alma süreçlerini destekleyen ve dijital dönüşüme katkı sağlayan güvenilir bir yapay zekâ platformu geliştirmektir.

### 🚀 Takım Üyeleri ve Görev Dağılımı

#### 👩‍✈️ Şükran Akşimşek (Takım Kaptanı)
**Projedeki Görevi:** Proje koordinasyonu, sistem mimarisinin tasarımı ve **LangGraph Agent** iş akışlarının kurgulanması.

#### 💻 Sıla Çakmak (Ekip Üyesi)
**Projedeki Görevi:** **LLM** geliştirme, veri ön işleme hatlarının kurulması, backend, model entegrasyonu ve **Full-stack** uygulama geliştirme.

#### 🗄️ İlknur Gençoğlu (Ekip Üyesi)
**Projedeki Görevi:** Mevzuat veri tabanı tasarımı, **RAG** sistem mimarisi, metin vektörleştirme (**Embedding**) süreçleri ve **PostgreSQL / pgvector** yönetimi.

#### 👁️ Tuğba Nur Başkaya (Ekip Üyesi)
**Projedeki Görevi:** **OCR** entegrasyonu, belge işleme, belge sınıflandırma ve eksik bilgi/belge tespit ajanlarının geliştirilmesi.

## 🎯 Projenin Amacı ve Hedefleri

LEGIVRA AI'ın temel amacı, kamu kurumlarında yürütülen evrak işleme süreçlerini tamamen otomatik hale getirmek değil; yapay zekâyı kamu personelinin yerine karar veren bir sistem olarak değil, personele karar desteği sunan güvenilir bir **dijital çalışma arkadaşı** olarak konumlandırmaktır.

### Problem Tanımı (Mevcut Durum)
Tarım ve Orman Bakanlığı merkez ve taşra teşkilatlarında her gün binlerce Çiftçi Destek Başvurusu, Hayvan Hastalığı İhbarı, Gıda Güvenliği Denetim Raporu ve Orman Yangını Bildirimi gibi evraklar işleme alınmaktadır. Bu süreçlerin manuel yürütülmesi; işlem sürelerinin uzamasına, personel üzerinde iş yükünün birikmesine, mevzuat takibinin zorlaşmasına, bilgi asimetrisine ve karar yorgunluğuna yol açmaktadır. Özellikle kritik ihbarların gözden kaçması ciddi kamu zararlarına neden olabilmektedir.

### Hedeflerimiz:
* Evrak işleme ve mevzuat araştırma sürelerini önemli ölçüde azaltmak.
* Kamu personelinin operasyonel iş yükünü hafifletmek ve yanlış birime yönlendirme oranını düşürmek.
* Eksik belge tespitini hızlandırmak ve resmî yazı oluşturma süreçlerini standartlaştırmak.
* Kritik evrakların gözden kaçmasını önlemek.
* Yapay zekâ kararlarının açıklanabilir, denetlenebilir ve KVKK ile uyumlu olmasını sağlamak.
* Modüler yapı ile farklı kamu kurumlarına kolayca uyarlanabilen ölçeklenebilir bir platform geliştirmek.

---

## 🛠️ Teknik Mimari ve Kullanılan Teknolojiler

LEGIVRA AI, mikro servis mantığıyla geliştirilen modüler, katmanlı (Layered Architecture) ve ölçeklenebilir bir platformdur.

### Teknoloji Yığını (Tech Stack)

| Katman | Teknoloji | Kullanım Amacı |
| :--- | :--- | :--- |
| **Backend** | FastAPI | REST servisleri ve API katmanı |
| **Frontend** | Streamlit | Kullanıcı arayüzü / dashboard gösterge paneli |
| **Agent Framework** | LangGraph | Çok ajanlı iş akışı ve durum yönetimi (`Workflow State`) |
| **LLM** | Gemini 2.5 Flash | Doğal dil üretimi, akıl yürütme ve yazı taslaklama |
| **RAG** | LangChain | Bilgi erişimi ve vektör arama orkestrasyonu |
| **OCR (Birincil)** | PaddleOCR | Doküman mizanpajı, evrak, tablo ve form yapılarını okuma |
| **OCR (Yedek)** | Tesseract | Hata toleransı ve fallback (ikinci deneme) katmanı |
| **Embedding** | BAAI bge-m3 | Türkçe semantik vektör üretimi |
| **Vector DB** | PostgreSQL + pgvector | Mevzuat semantik arama altyapısı |
| **Database** | PostgreSQL | Sistem kayıtları ve EBYS ilişkisel verileri |
| **Authentication** | JWT | Güvenli kimlik doğrulama |
| **Monitoring** | LangSmith | Yapay zekâ ajanlarının izlenmesi ve gözlemlenebilirlik |
| **Deployment** | Docker | Konteyner mimarisi ve kolay dağıtım |

### 🔍 Kritik Altyapı Kararları ve Mimari Gerekçeler

* **Neden LangGraph (CrewAI Değil)?** Projede evrakın durumuna göre (örn. eksik evrak senaryosu, düşük güven skoru) ajanlar arasında döngüsel (cyclic) bir akış ve koşullu karar mekanizmaları gerekmektedir. CrewAI ardışık (sequential) ekiplerde başarılıyken, LangGraph ajanları grafik düğümleri (node) olarak tanımlamaya ve durum yönetimini (state management) koşullu kenarlarla (conditional edges) hassas biçimde yapmaya olanak tanır.
* **Neden PostgreSQL + pgvector (Harici Vektör DB Değil)?** Kamu kurumlarındaki mevcut EBYS altyapıları ilişkisel veri tabanlarında çalışır. Verileri harici bir sisteme (Pinecone vb.) taşımak senkronizasyon riski yaratır. PostgreSQL + pgvector kullanımı, hem ilişkisel tabloları hem de mevzuat embedding'lerini tek bir veri tabanında ACID güvencesiyle saklayarak kurumsal üretime hazır (production-ready) bir yapı sunar.
* **Neden PaddleOCR + Tesseract Hibrit Yaklaşımı?** Gıda Güvenliği raporları matbu tablolardan, Hayvan Hastalığı İhbarları ise el yazısı formlardan oluşabilir. PaddleOCR doküman mizanpajını ve el yazısını klasik Tesseract'a göre daha yüksek kararlılıkla okur; Tesseract ise düşük güven skorlu durumlarda yedek (fallback) deneme katmanı olarak çalışır.

---

### Uçtan Uca Grafik Akışı

```mermaid
graph TD
    A[Vatandaş / Kurum Evrakı] --> B[Privacy Gateway]
    B --> C[Router - Orchestrator Agent]
    
    C --> D[OCR Agent]
    D --> E[Belge Sınıflandırma Agent]
    E --> F[Eksik Bilgi Kontrol Agent]
    F --> G[Risk & Öncelik Agent]
    G --> H[Legal RAG Agent]
    
    H --> I[Karar Destek / Birim Yönlendirme Agent]
    I --> J[Resmî Yazı Taslaklama Agent]
    J --> K[Audit & Compliance Agent]
    
    K --> L[İnsan Onayı Human-in-the-Loop]
    L --> M[EBYS Entegrasyon Agent]
    M --> N[Arşiv & Analitik Agent]
    N --> O([Bitiş])
    
    style A fill:#f9f9f9,stroke:#333,stroke-width:2px
    style C fill:#e1f5fe,stroke:#0288d1,stroke-width:2px
    style K fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    style L fill:#e8f5e9,stroke:#388e3c,stroke-width:2px
    style O fill:#eceff1,stroke:#607d8b,stroke-width:2px


### Öne Çıkan Ajanlar ve Görevleri:
1. **Gizlilik Katmanı (Privacy Gateway):** T.C. kimlik numarası, telefon, adres, e-posta ve vergi numarası gibi kişisel verileri analiz aşamasına aktarılmadan önce 6698 sayılı KVKK ilkelerine uygun olarak otomatik maskeler (Örn: `TR*********`).
2. **Yönlendirici Ajan (Router / Orchestrator Agent):** İş akışını başlatır, sistem durumunu izler, uygun ajanları dinamik geçişlerle tetikler ve hata durumunda alternatif akışları (karar ağacı mantığında) devreye alır. Doğrudan belge analizi yapmaz.
3. **Denetim ve Mevzuat Uyum Ajanı (Audit & Compliance Agent):** Büyük dil modellerinin halüsinasyon riskine karşı ikinci bağımsız doğrulama katmanıdır. Resmî yazı EBYS'ye gönderilmeden önce mevzuat uygunluğunu, yazışma formatını, eksik bilgi varlığını ve yazı ile mevzuat arasındaki çelişkileri denetler.

### 📋 Workflow State Veri Yapısı
Sistem, ajanlar arasında veri tutarlılığını ve hata toleransını sağlamak için şu alanları anlık izler:
* `Document ID`, `OCR Text`, `Document Type`, `Missing Fields`, `Risk Level`, `Legal References`, `Confidence Score`, `Generated Letter`, `Assigned Department`, `Approval Status`, `Current Agent / Step`.

---

## ⚖️ Güvenli RAG ve İnsan Denetimli İş Akışı (Human-in-the-Loop)

### RAG Mimarisi (Retrieval-Augmented Generation)
Büyük dil modellerinin yanlış veya güncel olmayan bilgi üretmesini önlemek amacıyla LLM hafızasından doğrudan yanıt üretmez (**Danger Path** engellenir). Önce ilgili kanun, yönetmelik, tebliğ ve genelgeler veri tabanından `BAAI bge-m3` embedding modeli ve cosine similarity kullanılarak aranır. Bulunan belgeler bağlam (`Context`) olarak modele iletilir ve model yalnızca bu doğrulanmış mevzuata dayanarak cevap üretir (**Safe Path**).

### Yapay Zekâ Güven Skoru (AI Confidence Score)
Toplam güven skoru aşağıdaki ağırlıklı bileşenler dikkate alınarak otomatik hesaplanır:

$$\text{Confidence} = \sum (w_i \times s_i)$$

| Bileşen | Ağırlık ($w$) |
| :--- | :--- |
| OCR | %20 |
| Belge Sınıflandırma | %20 |
| Mevzuat Eşleşmesi | %25 |
| Birim Yönlendirme | %15 |
| Resmî Yazı | %20 |

* **%90 – %100:** Öneri otomatik olarak personel onayına sunulur, revizyon beklenmez.
* **%70 – %89:** Öneri, dikkat çekici uyarı etiketiyle birlikte personele sunulur.
* **%70 Altı:** Zorunlu manuel inceleme başlatılır; süreç otomatik ilerlemez (`Human Review`).

---

## 🎬 Demo Senaryoları ve Risk Analizi

Sistemin gerçek kamu iş akışlarını yansıtabilmesi amacıyla, Tarım ve Orman Bakanlığı'nın süreçlerini temsil eden 4 uçtan uca senaryo kurgulanmıştır:

| Senaryo | Evrak Türü | Risk Seviyesi | Beklenen Sistem Davranışı |
| :--- | :--- | :--- | :--- |
| **1. Çiftçi Destek Başvurusu** | Dilekçe / Başvuru formu | 🟢 Normal | ÇKS belgesi eksikliği tespiti ➔ eksik belge bildirim yazısı taslağı ➔ ilgili müdürlüğe yönlendirme |
| **2. Gıda Güvenliği Denetim Raporu** | Taranmış matbu form / tablo | 🔴 Kritik | Tablo yapılı OCR okuma ➔ 5996 sayılı Kanun sunumu ve eşleştirme ➔ acil işlem kodlu yönlendirme (Zorunlu İnsan Onayı) |
| **3. Orman Yangını Sonrası Rehabilitasyon** | Resmî yazı / dilekçe | 🟠 Acil | Afet mevzuatı RAG sorgusu ➔ çoklu birim yönlendirme önerisi ➔ öncelikli işlem etiketi |
| **4. Hayvan Hastalığı İhbarı** | El yazısı form | 🔴 Kritik | El yazısı OCR ➔ anahtar ifade tespiti (şap, veteriner, numune) ➔ zorunlu insan onayı |

### 🚨 Risk Seviyesi Sınıflandırması
* **🟢 Normal:** Standart başvurular (Örn: Çiftçi destek başvurusu)
* **🟡 Orta:** Takip gerektiren işlemler (Örn: Rutin denetim raporu)
* **🟠 Acil:** Hızlı işlem gerektiren belgeler (Örn: Orman yangını rehabilitasyon talebi)
* **🔴 Kritik:** Kamu güvenliği/sağlığını doğrudan etkileyen belgeler (Örn: Hayvan hastalığı ihbarı, gıda güvenliği ihbarı)

---

## 🛡️ Fallback (Hata Yönetimi) Mekanizması

| Hata Durumu | Sistem Tepkisi |
| :--- | :--- |
| OCR başarısız | Tesseract ile yeniden dene |
| OCR tekrar başarısız | İnsan incelemesine aktar |
| RAG sonucu bulunamadı | Alternatif sorgu / genişletilmiş arama oluştur |
| LLM zaman aşımı | İkinci modeli çalıştır |
| Güven skoru düşük | Human-in-the-Loop'a yönlendir |
| EBYS bağlantısı kesildi | İşlemi kuyruğa al, otomatik yeniden dene |

---

## 📊 Performans Değerlendirme ve Hedef Metrikler

Kritik ihbarlarda (Hayvan Hastalığı, Gıda Güvenliği) yanlış negatiflerin (kritik evrakın gözden kaçması) maliyeti yüksek olduğundan, model performansının değerlendirilmesinde **Recall**'ı önceliklendiren **F2 Skoru** temel metrik olarak kullanılacaktır:

$$F_2 = \frac{5 \times (\text{Precision} \times \text{Recall})}{(4 \times \text{Precision}) + \text{Recall}}$$

### Hedef Değerler Tablosu

| Metrik | Amaç | Hedef Değer |
| :--- | :--- | :--- |
| Sınıflandırma Accuracy | Genel doğruluk | $\ge \%92$ |
| Precision | Yanlış pozitifleri azaltmak | $\ge \%88$ |
| Recall (Kritik Evraklar) | Kritik evrakları kaçırmamak | $\ge \%95$ |
| F1 Score | Genel denge | $\ge \%90$ |
| F2 Score | Recall'a ağırlık vermek | $\ge \%92$ |
| OCR CER / WER | OCR Karakter ve Kelime doğruluğu | $\le \%4$ / $\le \%8$ |
| RAGAS Faithfulness | Mevzuata bağlılık | $\ge 0.90$ |
| RAGAS Context Recall | Doğru bağlamın bulunması | $\ge 0.90$ |
| Ortalama İşlem Süresi | Uçtan uca performans | $\le 45 \text{ saniye / evrak}$ |

*Test aşamasında 4 demo senaryosunu kapsayan, en az 50-100 kurgusal evraktan oluşan bir değerlendirme (benchmark) seti hazırlanarak sonuçlar teknik raporda sunulacaktır.*

---

## 💼 Ticari Potansiyel ve Maliyet-Fayda (ROI) Analizi

Bir kurumda günde ortalama 200 evrak işlendiği varsayıldığında, pilot senaryo bazlı operasyonel kazanım hedefleri şu şekildedir:

| Gösterge | Manuel Süreç (Tahmini) | LEGIVRA ile (Hedef) |
| :--- | :--- | :--- |
| **Ortalama evrak işleme süresi** | 15 – 20 dakika | $\le 1 \text{ dakika}$ (otomatik ön analiz) + personel onayı |
| **Günlük personel başı evrak** | ~25 – 30 evrak | Personel yalnızca onay ve istisna evraklarına odaklanır |
| **Yanlış birime yönlendirme** | Değişken, izlenemiyor | Sistematik ölçüm + hedef $\le \%5$ |
| **Mevzuat araştırma süresi** | Evrak başına 5 – 10 dakika | Saniyeler içinde RAG ile otomatik öneri |

---

## 🔮 Yenilikçi Yönü ve Ölçeklenebilirlik

* **Yenilikçi Yönü:** Mevcut EBYS altyapıları sadece evrak kaydetmeye ve saklamaya odaklanırken; LEGIVRA AI, OCR, çok ajanlı yapay zekâ, Safe RAG, açıklanabilir yapay zekâ (XAI) ve güven skorlama mekanizmalarını tek platformda bir araya getiren bütüncül bir karar destek sistemidir.
* **Ölçeklenebilirlik:** Çekirdek ajan mimarisi değiştirilmeden; **Sağlık Bakanlığı, İçişleri Bakanlığı, Adalet Bakanlığı, Çevre, Şehircilik ve İklim Değişikliği Bakanlığı, Enerji ve Tabii Kaynaklar Bakanlığı** ve **Belediyelere** sadece ilgili kurumsal mevzuat seti RAG altyapısına eklenerek kolayca uyarlanabilir.

---
⚖️ *LEGIVRA AI - Kamu Hizmetlerinde Güvenilir ve Açıklanabilir Yapay Zekâ Dönüşümü.*
