# Promptla Web App — GitHub Pages ile telefonda çalıştırma

Tek dosyalık (`index.html`) statik web uygulaması. Telefonun kamerasıyla fotoğraf
çeker, **Gemini ile gerçek AI dönüşümü** yapar ve sonucu gösterir. Sunucu gerekmez —
GitHub Pages'te yayınlanır, telefondan tarayıcıyla açılır.

## Önce güvenlik (çok önemli)

- API anahtarı **koda/depoya yazılmaz.** Uygulama açıldığında ⚙️ Ayarlar'dan
  anahtarınızı girersiniz; anahtar **yalnızca telefonunuzun tarayıcı belleğinde**
  (localStorage) saklanır, hiçbir yere gönderilmez.
- Daha önce sohbette paylaştığınız anahtarı **iptal edin**, AI Studio'dan **yeni**
  bir anahtar alın: https://aistudio.google.com/apikey
- Anahtar `AIza...` ile başlamalıdır (Google AI Studio API anahtarı).

## GitHub Pages'e yükleme (adım adım)

1. GitHub'da yeni bir repo oluşturun (örn. `promptla-web`), **Public** veya Private.
2. Bu klasördeki dosyaları reponun **köküne** koyun: `index.html`, `.nojekyll`, `README.md`.
   - Git ile:
     ```bash
     cd webapp
     git init
     git add index.html .nojekyll README.md
     git commit -m "Promptla web app"
     git branch -M main
     git remote add origin https://github.com/KULLANICI/promptla-web.git
     git push -u origin main
     ```
3. Repo → **Settings → Pages** → "Build and deployment" → Source: **Deploy from a branch**
   → Branch: **main** / **/(root)** → Save.
4. 1–2 dakika sonra siteniz hazır: `https://KULLANICI.github.io/promptla-web/`
5. Bu adresi **telefon tarayıcısında** açın.

> Not: GitHub Pages **HTTPS** sunduğu için kamera (getUserMedia) telefonda sorunsuz çalışır.

## Telefonda kullanım

1. Adresi açın → ⚙️ Ayarlar → Gemini API anahtarınızı yapıştırın → Kaydet.
2. "Fotoğraf çek" → kamera açılır → deklanşöre basın.
3. Prompt yazın veya bir stil seçin. İsterseniz **Promptu geliştir** (profesyonel
   prompt üretir — anahtar varsa Gemini ile, yoksa zengin yerel şablonla).
4. **Üret** → çektiğiniz fotoğraf Gemini ile dönüştürülür, **önce/sonra** görünür.
5. **Paylaş** veya **İndir**.

## Ayarlar

- **Görsel modeli:** varsayılan `gemini-2.5-flash-image` (Nano Banana). Hesabınızda
  farklı bir görsel modeli etkinse Ayarlar'dan değiştirebilirsiniz
  (örn. `gemini-3-pro-image-preview`).

## Sorun giderme

- "Üretim hatası: ... API key not valid" → Ayarlar'dan geçerli bir `AIza...` anahtarı girin.
- "Yanıtta görsel yok" → model adı yanlış olabilir; Ayarlar'dan görsel üreten bir
  model adı yazın veya bölgenizde modelin görsel iznini kontrol edin.
- Kamera açılmıyor → tarayıcıya kamera izni verin; bazı tarayıcılarda izin verilmezse
  cihazın kendi kamera/dosya seçicisi açılır.
