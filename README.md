# CoBudget - Personal Expense Tracker

A full-stack expense tracking application designed for two users (Prady and Rishita) to manage shared finances with mobile APK generation.

## Features

- **Google OAuth Authentication** - Secure login with Google accounts
- **Income Tracking** - Monthly salary and carry-over management
- **Expense Management** - Categorized spending with payment methods
- **Financial Analytics** - Visual charts and spending insights
- **Mobile App** - Automatic Android APK generation via GitHub Actions
- **Real-time Dashboard** - Live financial overview and trends

## Technology Stack

- **Frontend**: React 18 + TypeScript + Tailwind CSS
- **Backend**: Express.js + PostgreSQL + Drizzle ORM
- **Mobile**: Capacitor for Android APK generation
- **Authentication**: Replit Auth with OpenID Connect
- **Charts**: Recharts for data visualization

## Mobile App Installation

1. **Automatic Build**: APK files are automatically generated on code pushes
2. **Download**: Get the latest APK from the "Releases" section
3. **Install**: Enable "Install unknown apps" on Android and tap the APK file

## Database Schema

- **Users**: Profile information and authentication
- **Income**: Monthly earnings tracking
- **Expenses**: Categorized spending records with analytics

## Development

```bash
npm install
npm run dev
```

## Deployment

The app automatically builds mobile APKs through GitHub Actions whenever code is pushed to the main branch.

## Authorized Users

- mpradyumna38@gmail.com (Prady)
- allikarishita.44@gmail.com (Rishita)

## Mobile Features

- Touch-optimized interface
- Native Android integration
- Offline capability
- Status bar integration
- Haptic feedback