# 🚀 TaskNotate

<p align="center">
  <img src="https://github.com/user-attachments/assets/c1ea1b69-76ea-4e86-9a35-c5393a96cd78" alt="TaskNotate Logo" width="150">
</p>

<p align="center"><em>Your ultimate productivity companion — customizable, powerful, and beautifully designed ⏰📝</em></p>

<div align="center">

![Flutter](https://img.shields.io/badge/Flutter-3.x-blue?style=for-the-badge&logo=flutter)
![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?style=for-the-badge&logo=dart)
![GetX](https://img.shields.io/badge/GetX-State%20Management-orange?style=for-the-badge)
![SQLite](https://img.shields.io/badge/SQLite-Embedded%20DB-003B57?style=for-the-badge&logo=sqlite)
![Local Notifications](https://img.shields.io/badge/Notifications-Local-blueviolet?style=for-the-badge&logo=bell)
![Clean Architecture](https://img.shields.io/badge/Architecture-Clean-green?style=for-the-badge)
![Kotlin](https://img.shields.io/badge/Kotlin-Android%20Native-7F52FF?style=for-the-badge&logo=kotlin)

</div>

---

## ✨ Features Overview

```mermaid
graph TD
    A[TaskNotate Features] --> B[🎯 Task Management]
    A --> C[⏰ Local Notifications]
    A --> D[🎨 Theme Customization]
    A --> E[🖌 Drawing & Notes]
    A --> F[🌍 Multi-language Support]
    A --> G[📅 Calendar & Timeline View]
    C --> H[Full-screen Alarm]
    C --> I[Lock Screen Support]
    C --> J[Reboot-resilient Scheduling]
```

---

## 🌈 Theme Showcase

### Default UI
<p align="center">
  <img src="https://github.com/user-attachments/assets/2c93d080-c4d7-4c56-9634-e00ca499894f" width="200">
  <img src="https://github.com/user-attachments/assets/bf83d76b-938c-4f65-9143-7d7159069337" width="200">
  <img src="https://github.com/user-attachments/assets/aa6804c6-f52f-4f94-9671-1ec1395f2195" width="200">
  <img src="https://github.com/user-attachments/assets/424a0979-e330-4cae-b7ea-f02fdc9459c3" width="200">
</p>

### More Screens
<p align="center">
  <img src="https://github.com/user-attachments/assets/fcf52824-5c8a-44a8-aa89-e18965c942b8" width="200">
  <img src="https://github.com/user-attachments/assets/308f7161-9d8f-44d8-9043-f1041d4a7b4c" width="200">
  <img src="https://github.com/user-attachments/assets/d9b499b4-6892-42c4-beb1-4744cd569459" width="200">
  <img src="https://github.com/user-attachments/assets/12cd8a00-601a-4d55-a7a8-0fe83dd9e052" width="200">
  <img src="https://github.com/user-attachments/assets/63be5816-b264-44ff-83ac-93909f3e8612" width="200">
  <img src="https://github.com/user-attachments/assets/9d8381e8-c85c-4cd2-b1d7-e1c9f636f5a1" width="200">
</p>

---

## 🧠 Why TaskNotate?

- 🚀 Clean & modular architecture (Clean + MVC)
- ⏰ Intelligent task scheduling with alarm fallback
- 🎨 Minimal UI designed for focus & clarity
- 🌐 Multilingual UI (🇬🇧 🇸🇦 🇪🇸 🇩🇪 🇨🇳)

---

## 🔔 Alarm System: Behind the Scenes

```mermaid
graph TD
    A[⏰ Alarm Trigger] --> B[Kotlin Alarm Handler]
    B --> C[MethodChannel Bridge]
    C --> D[Flutter Alarm Service]
    D --> E[Alarm State Notifier]
    E --> F[Alarm UI Screen]
```

> Full-screen persistent alarm with dismiss options and lock screen visibility.

---

## 🧱 Tech Stack

| 🔧 Component         | 🚀 Technology                   |
|----------------------|-------------------------------|
| Framework            | Flutter 3.x                   |
| Architecture         | Clean + MVC                   |
| State Management     | GetX                          |
| Local Storage        | SQLite                        |
| Alarm Scheduling     | flutter_local_notifications + alarm |
| Platform Integration | Kotlin                        |
| Drawing Engine       | CustomPaint API               |

---

## 🔁 Sample Code

### Kotlin — Alarm Activity

```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    if (intent?.action == "com.megoabkm.tasknotate.ALARM_TRIGGER") {
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O_MR1) {
            setShowWhenLocked(true)
            setTurnScreenOn(true)
        } else {
            window.addFlags(
                WindowManager.LayoutParams.FLAG_KEEP_SCREEN_ON or
                WindowManager.LayoutParams.FLAG_TURN_SCREEN_ON or
                WindowManager.LayoutParams.FLAG_SHOW_WHEN_LOCKED
            )
        }
    }
    super.onCreate(savedInstanceState)
}
```

### Dart — Alarm Handler

```dart
void _handleAlarmTrigger(AlarmSettings settings) async {
  await AlarmDisplayStateService.to.setAlarmScreenActive(true);
  Get.offAllNamed(AppRoute.alarmScreen, arguments: {
    'id': settings.id,
    'title': 'Task Reminder',
  });
}

Future<void> stopAlarm(int alarmId) async {
  await Alarm.stop(alarmId);
  await AlarmDisplayStateService.to.setAlarmScreenActive(false);
}
```

---

## 🧪 Try It Now

```bash
git clone https://github.com/MegoABKM/TaskNotate.git
cd TaskNotate
flutter pub get
flutter run
```

---

## 🤝 Contribute

<p align="center">
  <a href="https://github.com/MegoABKM/TaskNotate/pulls">
    <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen.svg?style=for-the-badge">
  </a>
  <a href="https://github.com/MegoABKM/TaskNotate/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge">
  </a>
</p>

> Made with 💙 using Flutter — Help us make it even better!
