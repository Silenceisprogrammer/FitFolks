# FiFolks 🏃

**Fitness for Everyone** — A culturally relevant, affordable fitness app for students and users in semi-urban and rural India.

## Features

- **Home Dashboard** — Daily motivation, workout recommendations, step tracking, water intake, challenge progress, and streak counting
- **Workout Library** — No-equipment workouts including Surya Namaskar, yoga asanas, and mobility routines
- **Camera Workout Tracking** — Mock pose estimation with rep counting, posture feedback, and form analysis (privacy-first, all processing local)
- **Nutrition** — Regional Indian and Odia food database with meal logging, budget-aware suggestions, and macro tracking
- **Challenges** — Heritage challenges (Lingaraj to Konark, Puri to Chilika), fitness challenges, and community events
- **Leaderboards** — Friends, college, hostel, and city rankings
- **Accountability Partners** — Invite friends, send encouragement, and set mutual reminders
- **Nearby Places** — Parks, running tracks, outdoor gyms, and walking routes
- **Progress Tracking** — Weekly activity, step trends, form score improvement, and monthly reports
- **Multilingual** — English, Odia (ଓଡ଼ିଆ), and Hindi (हिन्दी)
- **Dark/Light Mode** — Gradient-based theming with system preference support
- **Privacy-First** — All data stored locally, no camera footage uploaded

## Tech Stack

- **React Native** with **Expo** (SDK 57)
- **TypeScript** — Strict mode
- **Expo Router** — File-based routing
- **React Native Paper** — UI components
- **Zustand** — State management with AsyncStorage persistence
- **Expo Camera** — Camera-based workout tracking
- **Expo Linear Gradient** — Gradient-based theming
- **React Native SVG** — Charts and pose overlay visualization

## Getting Started

### Prerequisites

- Node.js 18+
- Expo Go app on your device (or Android/iOS emulator)

### Installation

```bash
# Install dependencies
npm install

# Start the development server
npx expo start
```

### Running on Device

1. Install **Expo Go** from the App Store or Google Play
2. Scan the QR code from the terminal with Expo Go
3. The app will load and you can start using it

### Running on Emulator

```bash
# Android
npx expo start --android

# iOS (macOS only)
npx expo start --ios
```

## Project Structure

```
FiFolks/
├── app/                    # Expo Router screens
│   ├── _layout.tsx         # Root layout with providers
│   ├── index.tsx           # Splash screen
│   ├── onboarding.tsx      # Onboarding flow
│   ├── (tabs)/             # Tab navigation
│   │   ├── index.tsx       # Home dashboard
│   │   ├── workouts.tsx    # Workout library
│   │   ├── nutrition.tsx   # Nutrition dashboard
│   │   ├── challenges.tsx # Challenges
│   │   └── profile.tsx    # Profile & settings
│   ├── workout-details.tsx
│   ├── camera-workout.tsx
│   ├── workout-complete.tsx
│   ├── add-meal.tsx
│   ├── meal-recognition.tsx
│   ├── food-details.tsx
│   ├── challenge-details.tsx
│   ├── leaderboard.tsx
│   ├── accountability.tsx
│   ├── nearby.tsx
│   ├── progress.tsx
│   ├── monthly-report.tsx
│   └── privacy.tsx
├── components/             # Reusable UI components
│   ├── ui/                 # GradientButton, GradientCard, etc.
│   ├── charts/             # ProgressChart, LineChart
│   └── workout/            # PoseOverlay
├── constants/              # Theme and color definitions
├── data/                   # Mock data (exercises, foods, challenges, etc.)
├── i18n/                   # Translations (en, od, hi)
├── services/               # Service abstractions
│   ├── poseTracking.ts     # Mock pose estimation adapter
│   ├── nutrition.ts        # Nutrition calculations
│   ├── mealRecognition.ts  # Mock AI meal recognition
│   ├── stepTracking.ts     # Step counting
│   ├── challenge.ts        # Challenge management
│   ├── location.ts         # Location services
│   └── report.ts           # Report generation
├── store/                  # Zustand stores
├── types/                  # TypeScript type definitions
└── utils/                  # Helper utilities
```

## Mock Services & Integration Points

The app uses mock services that are clearly separated and can be replaced with real implementations:

### PoseTrackingService
- **Current**: Mock adapter that simulates landmarks, rep counting, and posture feedback
- **Integration**: Replace with MediaPipe Pose, TensorFlow Lite MoveNet, or Expo Camera frame processors
- **Location**: `services/poseTracking.ts`

### MealRecognitionService
- **Current**: Mock recognition with confidence scores and editable results
- **Integration**: Replace with TensorFlow Lite food classification model or ONNX Runtime
- **Location**: `services/mealRecognition.ts`

### StepTrackingService
- **Current**: Mock step data
- **Integration**: Replace with expo-sensors Pedometer API or Google Fit
- **Location**: `services/stepTracking.ts`

### LocationService
- **Current**: Mock nearby places data
- **Integration**: Replace with OpenStreetMap Overpass API and expo-location
- **Location**: `services/location.ts`

## Privacy & Security

- **Local-First**: All data is stored on the device using AsyncStorage
- **No Uploads**: Camera footage is never uploaded to any server
- **Offline-First**: The app works without an internet connection
- **Transparent**: Clear privacy explanations during onboarding
- **User Control**: Delete all data option in Profile settings

## Design System

- **Gradient-Based**: All colors come from gradient pairs, no static palette
- **Dark/Light Mode**: Full theme support with system preference detection
- **Warm & Friendly**: Rounded cards, friendly illustrations, culturally appropriate copy
- **Accessible**: Large touch targets, high contrast, readable typography

## License

MIT
