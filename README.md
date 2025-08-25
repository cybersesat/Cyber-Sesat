# PWA Starter (Gratis)

Langkah cepat ubah situs/HTML jadi "aplikasi" yang bisa di-install (PWA).

## Cara pakai (paling mudah)
1) Upload semua file/folder ini ke root situs kamu (bareng `index.html`).
2) Edit `manifest.webmanifest`:
   - `name`, `short_name`: nama app.
   - `start_url` dan `scope`: untuk situs kamu, biasanya "/" sudah benar.
3) Edit `index.html`:
   - Ganti `YOUR_APP_NAME`.
   - Ganti `YOUR_SITE_URL` di tag `<iframe>` atau hapus iframe dan taruh konten asli situsmu.
4) Akses situs kamu dari Chrome/Edge/Brave (Android/desktop). Kamu akan lihat tombol "Install App" / "Add to Home Screen".

## Hosting gratis yang mudah
- GitHub Pages, Cloudflare Pages, Netlify (free tier). Cukup upload repo/folder ini.

## Catatan penting
- Banyak situs melarang di-embed (X-Frame-Options). Jika iframe tidak tampil, hapus iframe dan gunakan halaman ini sebagai beranda asli websitemu.
- PWA **harus** di-serve lewat HTTPS (kecuali di `localhost`).

## Build APK Android (opsional, gratis)
Kalau mau file APK dari situs kamu:
- Pakai **Capacitor** atau **Cordova**: webview yang memuat URL kamu.
  - Capacitor ringkas:
    ```bash
    npm create @capacitor/app@latest
    # Isi nama app, id (mis `com.namasaya.app`), pilih "Web App" dan isi URL situs kamu.
    cd <folder-app> && npx cap add android && npx cap open android
    # Build di Android Studio -> Generate Signed/Debug APK.
    ```
- Atau **Bubblewrap** (Trusted Web Activity) untuk situs PWA:
    ```bash
    npm i -g @bubblewrap/cli
    bubblewrap init --manifest https://DOMAIN-KAMU/manifest.webmanifest
    bubblewrap build
    ```
