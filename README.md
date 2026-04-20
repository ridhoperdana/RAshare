# RetroAchievements Share

Minimal, retro-styled website untuk share pencapaian RetroAchievements kamu.

## 🎮 Fitur

- ✨ **Retro Aesthetic** - CRT scanlines, pixel fonts, neon colors
- 🌓 **Dark/Light Mode** - Toggle tema dengan satu klik
- 📊 **Live Data** - Fetch real-time dari RetroAchievements API
- 📱 **Responsive** - Optimal buat share di X (Twitter) & Instagram
- ⚡ **Ringan** - Single HTML file, <20KB
- 🔐 **Secure** - API key terpisah dari source code

## 🚀 Setup Instructions

### 1. Clone Repository

```bash
git clone https://github.com/[YOUR-USERNAME]/retroachievements-share.git
cd retroachievements-share
```

### 2. Buat Config File

Copy template dan isi dengan API key kamu:

```bash
cp config.json.example config.json
```

Lalu edit `config.json`:

```json
{
  "username": "YOUR_RETROACHIEVEMENTS_USERNAME",
  "apiKey": "YOUR_API_KEY",
  "apiBaseUrl": "https://retroachievements.org"
}
```

**Cara dapat API Key:**
1. Login ke https://retroachievements.org/
2. Pergi ke: https://retroachievements.org/controlpanel.php
3. Cari "API Key" di bagian bawah

⚠️ **IMPORTANT:** `config.json` sudah di `.gitignore` dan **TIDAK AKAN** di-commit ke repository. Ini untuk melindungi API key kamu.

### 3. Update index.html

Edit bagian ini di `index.html` (sekitar line 260):

```javascript
const CONFIG = {
    username: 'YOUR_USERNAME',
    apiKey: 'YOUR_API_KEY',
    apiBaseUrl: 'https://retroachievements.org',
    recentAchievementsCount: 10
};
```

### 4. Deploy ke GitHub Pages

#### Cara 1: Manual via GitHub Web UI

1. Push ke GitHub:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

2. Buka repository di GitHub
3. Klik **Settings** > **Pages**
4. Source: pilih **Deploy from a branch**
5. Branch: **main** / **root**
6. Klik **Save**

#### Cara 2: Via GitHub CLI

```bash
gh repo create retroachievements-share --public --source=.
gh repo view --web
# Lalu ikuti Cara 1 langkah 3-6
```

### 5. Akses Website

Setelah deploy (butuh 1-2 menit):
- URL: `https://[YOUR-USERNAME].github.io/retroachievements-share/`

## 🎨 Customization

### Ganti Warna (CSS Variables)

Edit di `<style>` bagian `:root` dan `[data-theme="dark"]`:

```css
:root {
    --accent-primary: #00ff41;  /* Neon Green */
    --accent-secondary: #ff00ff; /* Neon Pink */
    --accent-tertiary: #00d9ff;  /* Neon Blue */
}
```

### Ganti Font

Ganti Google Fonts di `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323&display=swap" rel="stylesheet">
```

### Jumlah Recent Achievements

Edit di `CONFIG`:

```javascript
recentAchievementsCount: 10  // Ganti angkanya
```

## 📱 Share ke Social Media

### Twitter/X

1. Buka website di browser
2. Klik kanan > Copy image atau screenshot
3. Upload ke Twitter/X
4. Paste URL: `https://[YOUR-USERNAME].github.io/retroachievements-share/`

### Instagram

1. Screenshot website (rekomendasi: mode landscape)
2. Upload ke Instagram Feed/Stories
3. Add link di bio

## 🔒 Security Notes

- ✅ `config.json` sudah ada di `.gitignore` - **AMAN** dari commit
- ✅ API key kamu **TIDAK AKAN** pernah masuk ke repository
- ✅ Template tersedia di `config.json.example` untuk referensi
- ⚠️ **JANGAN pernah** men-share API key kamu secara publik
- ⚠️ Jika API key bocor, segera revoke di: https://retroachievements.org/controlpanel.php

## 🐛 Troubleshooting

### Data tidak muncul

1. Cek console browser (F12 > Console) untuk error
2. Verify API key: https://retroachievements.org/controlpanel.php
3. Test API manually:
   ```bash
   curl "https://retroachievements.org/API/API_GetUserSummary.php?u=YOUR_USERNAME&z=YOUR_USERNAME&y=YOUR_API_KEY"
   ```

### Theme tidak save

- Pastikan browser tidak dalam incognito/private mode
- Cek localStorage di DevTools (Application > Local Storage)

## 📊 API Endpoints Used

- `API_GetUserSummary.php` - User profile & stats
- `API_GetUserRecentAchievements.php` - Latest achievements

Full API docs: https://retroachievements.org/APIDocs.php

## 🎯 Future Enhancements

- [ ] Multi-user support (public leaderboard)
- [ ] Game completion progress
- [ ] Filter by console/game
- [ ] Achievement timeline/graph
- [ ] PWA support (offline mode)
- [ ] Compare with friends

## 📝 License

MIT - Bebas digunakan dan dimodifikasi

## 🙏 Credits

- [RetroAchievements](https://retroachievements.org/) - API & Platform
- [Press Start 2P](https://fonts.google.com/specimen/Press+Start+2P) - Pixel Font
- [VT323](https://fonts.google.com/specimen/VT323) - Monospace Font

---

**Made with ❤️ by cync48's Retro Gaming Journey**
