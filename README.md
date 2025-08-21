# PowerTrack - Aplikacja do śledzenia treningów siłowych

PowerTrack to minimalistyczna aplikacja webowa typu SaaS do śledzenia i zarządzania treningiem siłowym. Aplikacja pozwala użytkownikom monitorować swoje treningi, przeglądać historię ćwiczeń i śledzić postępy.

## 🚀 Funkcje (MVP)

- **Dashboard** - Podsumowanie treningów i statystyk
- **Dodawanie treningów** - Tworzenie nowych sesji treningowych
- **Zarządzanie ćwiczeniami** - Dodawanie ćwiczeń z seriami i powtórzeniami
- **Autoryzacja** - Logowanie przez Google OAuth
- **Responsywny design** - Działanie na wszystkich urządzeniach

## 🛠️ Technologie

- **Frontend**: Next.js 14, React, TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: Radix UI, Lucide React
- **Backend**: Next.js API Routes
- **Database**: PostgreSQL z Prisma ORM
- **Authentication**: NextAuth.js (Auth.js)
- **Deployment**: Vercel

## 📦 Instalacja

1. **Sklonuj repozytorium**
```bash
git clone <repository-url>
cd powertrack
```

2. **Zainstaluj zależności**
```bash
npm install
```

3. **Skonfiguruj zmienne środowiskowe**
Skopiuj plik `.env.example` do `.env` i uzupełnij wartości:

```env
# Database
DATABASE_URL="your-database-url"

# NextAuth
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-secret-key"

# Google OAuth
GOOGLE_CLIENT_ID="your-google-client-id"
GOOGLE_CLIENT_SECRET="your-google-client-secret"
```

4. **Skonfiguruj bazę danych**
```bash
# Wygeneruj klienta Prisma
npx prisma generate

# Uruchom migracje
npx prisma db push
```

5. **Uruchom aplikację**
```bash
npm run dev
```

Aplikacja będzie dostępna pod adresem `http://localhost:3000`

## 🔧 Konfiguracja Google OAuth

1. Przejdź do [Google Cloud Console](https://console.cloud.google.com/)
2. Utwórz nowy projekt lub wybierz istniejący
3. Włącz Google+ API
4. Utwórz OAuth 2.0 credentials
5. Dodaj `http://localhost:3000/api/auth/callback/google` do Authorized redirect URIs
6. Skopiuj Client ID i Client Secret do pliku `.env`

## 📁 Struktura projektu

```
src/
├── app/                    # Next.js App Router
│   ├── api/               # API routes
│   ├── auth/              # Strony autoryzacji
│   ├── workout/           # Strony treningów
│   └── globals.css        # Globalne style
├── components/            # Komponenty React
│   └── ui/               # Komponenty UI
├── lib/                  # Biblioteki i konfiguracja
│   ├── auth.ts           # Konfiguracja Auth.js
│   ├── prisma.ts         # Klient Prisma
│   └── utils.ts          # Funkcje pomocnicze
└── types/                # Definicje TypeScript
```

## 🚀 Deployment

### Vercel (zalecane)

1. Połącz repozytorium z Vercel
2. Dodaj zmienne środowiskowe w panelu Vercel
3. Wdróż aplikację

### Inne platformy

Aplikacja może być wdrożona na dowolnej platformie obsługującej Next.js.

## 🤝 Rozwój

### Dodawanie nowych funkcji

1. Utwórz nową gałąź: `git checkout -b feature/nazwa-funkcji`
2. Wprowadź zmiany
3. Przetestuj lokalnie
4. Utwórz Pull Request

### Struktura bazy danych

Aplikacja używa następujących modeli:
- **User** - Użytkownicy aplikacji
- **Workout** - Treningi użytkowników
- **Exercise** - Ćwiczenia w treningach
- **Set** - Serie ćwiczeń

## 📝 Licencja

MIT License - zobacz plik [LICENSE](LICENSE) dla szczegółów.

## 🆘 Wsparcie

Jeśli masz pytania lub problemy, utwórz issue w repozytorium lub skontaktuj się z zespołem deweloperskim.
