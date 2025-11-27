# Dyscover

**Aplikasi Skrining dan Terapi Disleksia untuk Anak**

Dyscover adalah aplikasi mobile yang dirancang untuk membantu mendeteksi dan menangani disleksia pada anak melalui skrining berbasis suara dan fitur gamifikasi interaktif. Aplikasi ini menggunakan teknologi speech recognition untuk menganalisis kemampuan membaca anak dan memberikan rekomendasi terapi yang sesuai.

## 🏆 Pencapaian

**Juara 3 - Hackathon elevAIte Indonesia 2025 Hub UGM**

Aplikasi ini meraih juara 3 dalam kompetisi hackathon elevAIte Indonesia 2025 yang diselenggarakan oleh Hub UGM, mengalahkan ratusan peserta lainnya dengan inovasi dalam bidang AI untuk pendidikan dan kesehatan anak.

## ✨ Fitur Utama

### 1. **Skrining Disleksia**

- **Quick Screening (Tes Baca Ucapan)**: Tes membaca huruf dan kata menggunakan teknologi speech recognition
- **Grade-Level Reading**: Penilaian tingkat kelas untuk mengukur kemampuan membaca sesuai usia
- **Analisis Real-time**: Sistem menganalisis pelafalan pengguna secara real-time
- **Laporan Hasil Detil**: Menampilkan akurasi, tingkat risiko, dan rekomendasi langkah selanjutnya

### 2. **Gamifikasi Interaktif**

- **Menulis Karakter**: Latihan menulis huruf dan karakter
- **Latihan Ejaan**: Permainan untuk meningkatkan kemampuan spelling
- **Suara dan Huruf**: Latihan pengenalan fonemik dan hubungan suara-huruf
- **Urut Kata**: Permainan menyusun kata untuk melatih kemampuan membaca

### 3. **Tips dan Edukasi**

- Koleksi tips untuk membantu anak dengan disleksia
- Informasi edukatif tentang disleksia dan cara menanganinya
- Panduan untuk orang tua dan pendidik

### 4. **Riwayat Screening**

- Penyimpanan hasil screening sebelumnya
- Tracking perkembangan dari waktu ke waktu
- Analisis trend kemampuan membaca

### 5. **Timer dan Progress Tracking**

- Timer otomatis untuk mengukur durasi screening
- Progress bar untuk menunjukkan kemajuan tes
- Statistik akurasi dan waktu penyelesaian

## 🛠️ Teknologi yang Digunakan

### Frontend

- **React Native** (v0.79.2) - Framework untuk pengembangan aplikasi mobile
- **Expo** (~53.0.9) - Platform untuk pengembangan React Native
- **Expo Router** (~5.0.6) - File-based routing untuk navigasi
- **TypeScript** (~5.8.3) - Type-safe JavaScript

### Libraries Utama

- **@react-native-voice/voice** (^3.2.4) - Speech recognition untuk analisis suara
- **React Context API** - State management untuk screening dan timer
- **Expo Linear Gradient** - UI gradients
- **React Native Vector Icons** - Icon library

### Backend Integration

- API endpoint untuk fetching data screening test
- Fallback data untuk offline functionality

## 📱 Platform Support

- ✅ **Android** - Native support dengan permissions untuk microphone
- ✅ **iOS** - Native support dengan speech recognition
- ✅ **Web** - Responsive web version

## 🚀 Instalasi dan Setup

### Prerequisites

- Node.js (v18 atau lebih baru)
- npm atau yarn
- Expo CLI
- Android Studio (untuk Android development)
- Xcode (untuk iOS development, macOS only)

### Langkah Instalasi

1. **Clone repository**

   ```bash
   git clone <repository-url>
   cd Dyscover
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Start development server**

   ```bash
   npx expo start
   ```

4. **Run pada platform tertentu**

   ```bash
   # Android
   npm run android

   # iOS
   npm run ios

   # Web
   npm run web
   ```

## 📁 Struktur Project

```
Dyscover/
├── app/                    # File-based routing (Expo Router)
│   ├── home/              # Halaman utama dan screening
│   │   ├── page.tsx       # Home page
│   │   ├── screening.tsx  # Quick screening test
│   │   ├── screening-advance.tsx  # Grade-level reading
│   │   ├── screening-instruction.tsx  # Instruksi screening
│   │   ├── screening-report.tsx  # Laporan hasil
│   │   ├── tips.tsx       # Tips dan edukasi
│   │   └── berita.tsx     # Berita terkait
│   ├── permainan/         # Fitur gamifikasi
│   │   ├── page.tsx       # Daftar permainan
│   │   └── menulis.tsx    # Game menulis
│   ├── riwayat/           # Riwayat screening
│   ├── auth/              # Autentikasi
│   └── onboarding/        # Onboarding screens
├── components/
│   ├── backend/           # Backend services
│   │   ├── screeningService.ts  # API integration
│   │   ├── voiceRecognition.tsx  # Speech recognition
│   │   └── askPermission.tsx     # Permission handling
│   ├── context/           # React Context providers
│   │   ├── ScreeningContext.tsx  # State management screening
│   │   └── TimerContext.tsx      # Timer state management
│   └── ui/                # Reusable UI components
│       ├── Button.tsx
│       ├── MicButton.tsx
│       ├── ProgressBar.tsx
│       └── SpeakerButton.tsx
├── assets/                # Images, fonts, icons
└── app.json               # Expo configuration
```

## 🎯 Fitur Teknis Detail

### Speech Recognition

- Menggunakan `@react-native-voice/voice` untuk capture audio
- Real-time transcription dari suara ke teks
- Perbandingan otomatis dengan expected word
- Timeout handling (10 detik per kata)
- Error handling dan retry mechanism

### Screening Flow

1. **Instruksi** → User membaca petunjuk screening
2. **Quick Screening** → Tes membaca huruf (alphabet test)
3. **Halfway** → Transisi antara tes
4. **Grade-Level Reading** → Tes membaca kata (word test)
5. **Laporan** → Hasil dengan akurasi, durasi, dan rekomendasi

### Timer System

- Start time dicatat saat button "Mulai" diklik
- End time dicatat saat tes selesai
- Format durasi: "X menit Y detik" atau "X detik"
- Display di laporan hasil screening

### State Management

- **ScreeningContext**: Mengelola data tes, scores, dan progress
- **TimerContext**: Mengelola start/end time untuk durasi screening
- Context providers di root layout untuk global access

## 🎨 Design System

### Colors

- Primary: `#8800cc` / `#8300BA` (Purple)
- Secondary: `#FFD233` (Yellow)
- Background: `#FFFFFF` (White)
- Error: `#FF3B3B` (Red)
- Success: `#00C853` (Green)

### Typography

- **Plus Jakarta Sans** - Font utama
- **Montserrat** - Font sekunder

### UI Components

- Custom button components dengan gradient support
- Progress bar dengan variant gradient
- Card-based layout untuk konten
- Tab navigation untuk fitur utama

## 📊 API Integration

### Screening Test API

- **Endpoint**: `https://dyslexia-backend.vercel.app/api/screening`
- **Response**:
  ```json
  {
    "alphabet_test": [["y", "p", "e"], ...],
    "word_test": ["proyek", "matahari", ...]
  }
  ```
- **Fallback**: Data default jika API tidak tersedia

## 🔒 Permissions

### Android

- `RECORD_AUDIO` - Untuk speech recognition
- `INTERNET` - Untuk API calls

### iOS

- Microphone permission
- Speech recognition permission

## 🧪 Testing

Untuk menjalankan linter:

```bash
npm run lint
```

## 📝 Lisensi

Private project - All rights reserved

## 👥 Tim Development

Dikembangkan oleh tim Ambatuwin untuk Hackathon elevAIte Indonesia 2025 Hub UGM.

## 🤝 Kontribusi

Project ini adalah hasil dari hackathon dan saat ini dalam tahap pengembangan aktif. Untuk pertanyaan atau kolaborasi, silakan hubungi tim development.

## 📞 Kontak

Untuk informasi lebih lanjut tentang aplikasi atau kolaborasi, silakan hubungi tim development.

---

**Dibuat dengan ❤️ untuk membantu anak-anak dengan disleksia**
