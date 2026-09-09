# Exp_1 — Hello World Android App

A simple Android application built with **Kotlin** that displays custom text on screen using a `TextView` inside a `ConstraintLayout`. Created as Experiment 1 for Mobile Application Development.

## 📱 Features
- Single-activity Android app (`MainActivity.kt`)
- `ConstraintLayout`-based UI with a centered `TextView`
- Edge-to-edge display with window insets handling
- Tested on an Android Emulator (API 33)

## 🛠️ Built With
- **Language:** Kotlin
- **Min SDK:** 24
- **Target SDK:** 36
- **Compile SDK:** 36
- **AGP (Android Gradle Plugin):** 9.3.1
- **Libraries:** AndroidX Core KTX, AppCompat, Activity KTX, ConstraintLayout, Material

## 📂 Project Structure
```
Exp_1/
├── app/
│   ├── build.gradle.kts
│   └── src/
│       ├── main/
│       │   ├── java/com/example/exp_1/
│       │   │   └── MainActivity.kt
│       │   ├── res/
│       │   │   ├── layout/activity_main.xml
│       │   │   ├── values/strings.xml
│       │   │   ├── values/colors.xml
│       │   │   └── values/themes.xml
│       │   └── AndroidManifest.xml
│       ├── androidTest/java/com/example/exp_1/ExampleInstrumentedTest.kt
│       └── test/java/com/example/exp_1/ExampleUnitTest.kt
├── gradle/libs.versions.toml
├── build.gradle.kts
├── settings.gradle.kts
├── screenshots/
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Android Studio (latest stable version)
- Android SDK with API 36 installed
- An emulator or physical device (minimum API 24)

### Installation
1. Clone the repository
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   ```
2. Open the project folder in **Android Studio**
3. Let Gradle sync complete
4. Run the app on an emulator or connected device using the **Run ▶** button

## 📄 Key Code

**`MainActivity.kt`**
```kotlin
package com.example.exp_1

import android.os.Bundle
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main)
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->
            val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
            insets
        }
    }
}
```

**`activity_main.xml`**
```xml
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Mobile Application Development"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## 📸 Screenshots
| Default Output | Custom Text | Final Output |
|---|---|---|
| ![Default](screenshots/Screenshot%202026-07-25%20080919.png) | ![Custom](screenshots/Screenshot%202026-07-25%20081239.png) | ![Final](screenshots/Screenshot%202026-07-25%20081409.png) |

## 🎯 Output
The app runs successfully on an Android emulator and displays the text `"Mobile Application Development"` on screen, confirming a correctly configured basic Android project.

## 👤 Author
**hritik harsh**

## 📃 License
This project is open source and available for educational use.
