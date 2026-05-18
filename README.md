# CinemaShare 🎬

Програма для спільного перегляду фільмів через Firebase з темним дизайном Netflix-стилю.

## Можливості

✅ **Аутентифікація** - Реєстрація та вхід через Firebase Auth
✅ **Кімнати для перегляду** - Відкриті та закриті кімнати
✅ **Синхронізація відео** - Спільний перегляд фільмів у реальному часі
✅ **Чат** - Спілкування учасників під час перегляду
✅ **Dark Theme** - Netflix-стиль темний дизайн
✅ **ExoPlayer** - Потужний відеоплеєр на весь екран
✅ **Android 10+** - Мінімальна версія Android 10

## Технологічний стек

- **Language**: Kotlin
- **Architecture**: MVVM + Repository Pattern
- **Database**: Firebase Realtime Database
- **Authentication**: Firebase Authentication
- **Video Player**: ExoPlayer (Media3)
- **Dependency Injection**: Dagger Hilt
- **Async**: Coroutines + LiveData
- **UI**: Material Design 3, Dark Theme

## Структура проекту

```
app/src/main/
├── kotlin/com/cinemashare/app/
│   ├── data/
│   │   ├── model/          # Data models (Room, User, Message)
│   │   └── repository/     # Repository classes
│   ├── ui/
│   │   ├── activity/       # Activities
│   │   ├── fragment/       # Fragments
│   │   └── viewmodel/      # ViewModels
│   ├── di/                 # Dependency Injection
│   └── CinemaShareApp.kt   # Application class
└── res/                    # Resources
```

## Встановлення

1. Клонуйте репозиторій
2. Налаштуйте Firebase проект:
   - Завантажте `google-services.json` з Firebase Console
   - Помістіть його в папку `app/`
3. Збудуйте проект в Android Studio
4. Запустіть на пристрої з Android 10+

## Firebase Налаштування

### Realtime Database Rules
```json
{
  "rules": {
    "rooms": {
      "$roomId": {
        ".read": true,
        ".write": "auth != null",
        "members": {
          ".write": "auth != null"
        },
        "messages": {
          "$messageId": {
            ".write": "auth != null"
          }
        }
      }
    },
    "users": {
      "$userId": {
        ".read": "auth != null",
        ".write": "auth.uid == $userId"
      }
    }
  }
}
```

## Розробка

- Gradle Build System
- Kotlin DSL для конфігурації
- Material Components для UI
- Coroutines для асинхронних операцій

## Ліцензія

MIT License

## Контакти

Якщо у вас є запитання або пропозиції, будь ласка, відкрийте issue.
