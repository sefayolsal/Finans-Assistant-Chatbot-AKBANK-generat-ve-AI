# Finans-Assistant-Chatbot-AKBANK-generat-ve-AI
# 💹 Finans Asistanı (RAG Chatbot)

Finans Asistanı, **LangChain**, **Google Gemini**, **HuggingFace**, **Chroma** ve **Gradio** kullanarak geliştirilmiş, bağlam korumalı (RAG destekli) bir yapay zekâ sohbet uygulamasıdır.
Kullanıcıların faiz oranları, hisse senetleri, tahviller, yatırım araçları, para politikaları ve benzeri finansal konularda doğru ve sade açıklamalar almasını sağlar.

---

## 🚀 Özellikler

* 🧠 **RAG (Retrieval-Augmented Generation)** mimarisi
* 💬 **Bağlam korumalı sohbet** (önceki mesajları hatırlama)
* 📊 **Finansal veri tabanından bilgi getirme**
* 🌐 **Google Gemini (GenAI) veya Hugging Face modelleri** ile entegrasyon
* 🧩 **Chroma vektör veritabanı** kullanımı
* 🪶 **Gradio arayüzü** (kolay kullanımlı web sohbet ekranı)

---

## ⚙️ Kurulum Kılavuzu

### 1️⃣ Sanal ortam oluşturma

```bash
python -m venv venv
# Windows:
venv\Scripts\activate
# Mac / Linux:
source venv/bin/activate
```

---

### 2️⃣ Gerekli kütüphanelerin yüklenmesi

Proje dizinine `requirements.txt` dosyasını oluştur ve aşağıdakileri ekle:

```txt
langchain==0.3.7
langchain-text-splitters==0.3.1
langchain-community==0.3.6
langchain-chroma==0.1.4
langchain-huggingface==0.0.3
python-dotenv==1.0.1
gradio==4.44.0
sentence-transformers==3.2.1
datasets==3.0.2
```

Ardından terminalde:

```bash
pip install -r requirements.txt
```

---

### 3️⃣ `.env` dosyası oluşturma

Proje kök dizinine `.env` adlı bir dosya ekle ve içine **Google API anahtarını** yaz:

```env
GOOGLE_API_KEY=AIzaSyXXXXXX
```

> ⚠️ Bu dosyayı `.gitignore` içine eklemeyi unutma, anahtarını GitHub’da paylaşma.

---

### 4️⃣ Uygulamayı çalıştırma

```bash
python app.py
```

Uygulama çalıştığında terminalde şu şekilde bir bağlantı görünür:

```
Running on public URL: https://xxxx.gradio.live
```
<img width="1594" height="850" alt="mikroeko2" src="https://github.com/user-attachments/assets/6a9c5857-e8fa-4ca8-aa17-ebcedd2a1c54" />


Bu bağlantıya tıklayarak sohbet arayüzüne erişebilirsin. 💬

---

## 🧩 Proje Yapısı

```
📁 finance-assistant/
│
├── app.py                 # Ana Python dosyası (chatbot arayüzü)
├── requirements.txt       # Gerekli kütüphaneler
├── .env                   # Google API anahtarı
├── chroma_db/             # Vektör veritabanı dizini
└── README.md              # Bu kılavuz
```

---

## 🧠 Çalışma Mantığı (Özet)

1. Finans verileri HuggingFace dataset’inden yüklenir.
2. Her kayıt, **SentenceTransformer** modeli ile embedding’e dönüştürülür.
3. Belgeler **Chroma vektör veritabanına** kaydedilir.
4. Kullanıcı bir soru sorduğunda:

   * `retrieve_context()` aracı benzer belgeleri getirir.
   * **LangChain agent** bu bilgileri kullanarak bağlamlı yanıt üretir.
5. Yanıt, Gradio arayüzünde kullanıcıya gösterilir.

---

## 🧪 Test / Değerlendirme

Model yanıtlarının doğruluğu, **cosine similarity** yöntemiyle otomatik olarak ölçülür.
Bu test `evaluate_answer()` fonksiyonu ile örnek QA setlerinde yapılabilir.

---


## 👨‍💻 Geliştirici Notu

Bu proje, finansal eğitim ve farkındalık amaçlı geliştirilmiştir.
Yatırım tavsiyesi **vermez**.
Modelin verdiği yanıtlar bilgilendirme amaçlıdır.

---

## 🪪 Lisans

Bu proje [MIT Lisansı](LICENSE) kapsamında paylaşılmaktadır.

---
