---
title: "Android Development with Kotlin: A Beginner’s Guide"
date: 2024-01-30
lastmod: 2025-06-24
draft: false
description: "Welcome to the exciting world of Android app development with Kotlin!"
categories: ["Technology"]
tags: ["android", "kotlin", "mobile-development", "beginner-guide"]
author: "Jonayed Hossan Gazi"
showToc: true
---

Welcome to the exciting world of Android app development with Kotlin! This guide is designed for individuals with a background in web development and scripting languages like Python or PHP, who are looking to transition into native Android development. We’ll cover the fundamental concepts of Android, introduce you to the Kotlin programming language in the context of Android, and prepare you to build your first application.

Android development can seem daunting at first due to its unique ecosystem, but with your existing programming knowledge, you’ll find many concepts transferable. We’ll break down the core components and tools, ensuring you gain a solid understanding of how Android applications are structured and how they interact with the system.

This guide will cover:

  * **Android Basics with Compose** : An overview of the recommended modern toolkit for building Android UIs.
  * **Android Manifest** : The blueprint of your Android application.
  * **Activities** : The building blocks of your app’s user interface.
  * **Permissions** : How Android apps request and manage access to sensitive data and system features.
  * **Gradle** : The powerful build system behind Android projects.



Let’s begin your journey into creating robust and engaging Android applications!

## Android Basics with Compose

Android Basics with Compose is a self-paced, online course provided by Google that teaches individuals, even those with no prior programming experience, how to build simple Android apps using Jetpack Compose. Jetpack Compose is Android’s modern toolkit for building native user interfaces. It simplifies and accelerates UI development on Android with less code, powerful tools, and intuitive Kotlin APIs. For developers coming from web backgrounds, thinking of Jetpack Compose might be similar to how modern web frameworks like React or Vue handle UI components and state management, where you declare what the UI should look like, and the framework takes care of updating it when the underlying data changes.

This course covers fundamental programming concepts and the basics of the Kotlin programming language within the context of Android development. It guides learners through using Android Studio, the official IDE for Android development, to build a collection of Android applications. The curriculum is structured into several units, each focusing on different aspects of app development:

  * **Unit 1: Your first Android app** : This unit introduces programming basics, guides users through installing Android Studio, and helps them build a simple Android app with a basic user interface that displays text and images. It also covers running the app on a device or emulator.
  * **Unit 2: Building app UI** : This unit delves deeper into Kotlin fundamentals, including conditionals, function types, classes, and lambda expressions. It explains how composition and recomposition work in Compose and teaches how to create interactive app UIs by adding buttons and handling user input. It also introduces state management and unit testing.
  * **Unit 3: Display lists and use Material Design** : This unit focuses on building apps that display lists of data, utilizing Kotlin’s data classes, functions, and collections. It covers creating scrollable lists, adding click listeners, and enhancing app aesthetics with Material Design principles, including colors, shapes, and typography.
  * **Unit 4: Navigation and app architecture** : This unit explores best practices for app architecture, focusing on building more complex applications. It covers activities and their lifecycles, modern Android architecture patterns (like StateFlow and UDF), ViewModel for data persistence, and the Navigation component for managing screen transitions. It also touches upon responsive UI design for different screen sizes.
  * **Unit 5: Connect to the internet** : This unit introduces Kotlin coroutines for asynchronous operations and explains how to perform network requests using HTTP and REST with Retrofit. It also covers displaying images from the internet using the Coil library and implementing dependency injection for better code organization.
  * **Unit 6: Data persistence** : This unit teaches how to store data locally on the device using SQLite databases with the Room library. It also covers using Database Inspector for debugging and Preference DataStore for storing user preferences.
  * **Unit 7: WorkManager** : This unit focuses on using Android Jetpack’s WorkManager API to schedule background tasks that persist even if the app exits or the device restarts, such as data backups or content downloads.
  * **Unit 8: Views and Compose** : This unit addresses interoperability between Jetpack Compose and the older View-based UI toolkit. It teaches how to use both paradigms side-by-side in the same app, allowing developers to integrate new Compose features into existing View-based applications or utilize existing View-based libraries within Compose projects.



This structured approach ensures a gradual learning curve, building foundational knowledge before moving on to more complex topics. The emphasis on Jetpack Compose aligns with current Android development best practices, making it an excellent starting point for new developers [1].

## The Android Manifest: Your App’s Blueprint

Every Android application must have an `AndroidManifest.xml` file in its root directory. This XML file serves as a blueprint for your app, providing essential information to the Android build tools, the Android operating system, and Google Play. It’s a declaration of your app’s components, capabilities, and requirements. For those with a web development background, you can think of the `AndroidManifest.xml` file as being conceptually similar to a combination of a `package.json` file (which defines metadata and dependencies) and a server configuration file (which defines routes and capabilities).

### Core Components of the Android Manifest:

  1. **App Components** : The manifest is where you declare all of your app’s components. This includes: 
     * **Activities (``)**: These are the screens of your app. Each activity you create must be declared in the manifest so the system knows it exists and can launch it.
     * **Services (``)**: These are components that run in the background to perform long-running operations or to supply data for other applications.
     * **Broadcast Receivers (``)**: These components listen for and respond to system-wide broadcast announcements.
     * **Content Providers (``)**: These components manage a shared set of app data.
  2. **Permissions (``)**: To access sensitive user data (like contacts or SMS) or certain system features (like the camera or internet), your app must request permission. You declare these permissions in the manifest. We’ll delve deeper into permissions in a later section.
  3. **Device Compatibility (`` and ``)**: The manifest is where you specify the hardware and software features your app requires. This information is used by Google Play to filter which devices can install your app. For example, you can require a device to have a camera or a specific version of the Android OS.



### Key Attributes and Elements:

  * **`package`** : This attribute in the `` element defines the unique package name for your application. This is used as a unique identifier for your app on the device and in the Google Play Store.
  * **`application`** : This element is a container for all the app’s components. It has attributes that apply to the entire application, such as the app’s icon, label, and theme.
  * **`intent-filter`** : This element within a component’s declaration specifies the types of intents the component can respond to. An intent is a messaging object you can use to request an action from another app component. For example, an intent filter can declare that an activity can be launched by the system’s launcher, making it the main entry point of your app.



Here’s a simple example of an `AndroidManifest.xml` file:

```
xml version="1.0" encoding="utf-8"?>
    <manifest xmlns:android="http://schemas.android.com/apk/res/android"
        package="com.example.myapp">
    
        <application
            android:allowBackup="true"
            android:icon="@mipmap/ic_launcher"
            android:label="@string/app_name"
            android:roundIcon="@mipmap/ic_launcher_round"
            android:supportsRtl="true"
            android:theme="@style/Theme.MyApp">
            <activity
                android:name=".MainActivity"
                android:exported="true">
                <intent-filter>
                    <action android:name="android.intent.action.MAIN" />
    
                    <category android:name="android.intent.category.LAUNCHER" />
                intent-filter>
            activity>
        application>
    
    manifest>
    

```
In this example, we have a single activity, `MainActivity`, which is declared as the main entry point of the app. The `intent-filter` tells the system that this activity should be added to the system’s app launcher.

Understanding the `AndroidManifest.xml` file is fundamental to Android development. It’s the central place where you define the structure and metadata of your app, and it’s the first thing the Android system looks at when it wants to run your application [2].

## Gradle: The Android Build System

Gradle is an advanced build automation system used by Android Studio to compile, build, and package your Android application or library. For those familiar with web development, you can think of Gradle as being similar to tools like Webpack, Gulp, or Grunt, but specifically tailored for the Android ecosystem. It handles everything from compiling your Kotlin code and resources to signing your application for release.

### What is a Build System?

A build system transforms your source code into an executable application. This process often involves multiple steps:

  * **Compiling** : Converting your Kotlin code into bytecode.
  * **Packaging** : Bundling all your code, resources (images, layouts, strings), and assets into an APK (Android Package Kit) file.
  * **Signing** : Digitally signing your APK to verify its authenticity and ensure it hasn’t been tampered with.
  * **Optimizing** : Reducing the size of your app and obfuscating code for security.



Gradle uses a task-based approach, where each step in the build process is a ‘task’. These tasks are defined by plugins, such as the Android Gradle Plugin (AGP), which provides all the necessary tasks for building Android applications.

### Key Concepts in Gradle:

  1. **Build Files** : Gradle builds are configured using build scripts, typically named `build.gradle` (for Groovy DSL) or `build.gradle.kts` (for Kotlin DSL). Android Studio projects usually have two main build files: 
     * **Project-level`build.gradle`**: This file defines build configurations that apply to all modules in your project. It often includes settings for repositories where dependencies are fetched and global configurations.
     * **Module-level`build.gradle`**: Each module (e.g., your app module, library modules) has its own `build.gradle` file. This is where you configure module-specific settings, such as dependencies, `minSdkVersion`, `targetSdkVersion`, and build types.
  2. **Plugins** : Plugins extend Gradle’s capabilities by adding new tasks and configurations. The most important plugin for Android development is the `com.android.application` plugin (for app modules) or `com.android.library` plugin (for library modules), which is part of the Android Gradle Plugin (AGP).
  3. **Dependencies** : Android projects often rely on external libraries to provide functionality (e.g., networking, image loading, UI components). Gradle makes it easy to declare and manage these dependencies. You specify them in your module-level `build.gradle` file, and Gradle automatically downloads and includes them in your project. 

```
// Example of dependencies in a module-level build.gradle.kts file
         dependencies {
             implementation("androidx.core:core-ktx:1.13.1")
             implementation("androidx.lifecycle:lifecycle-runtime-ktx:2.8.2")
             implementation("androidx.activity:activity-compose:1.9.0")
             implementation(platform("androidx.compose:compose-bom:2024.06.00"))
             implementation("androidx.compose.ui:ui")
             // ... other dependencies
         }
         

```
4. **Build Variants** : Gradle allows you to create different versions of your app from a single codebase. This is achieved through build types (e.g., `debug`, `release`) and product flavors (e.g., `free`, `paid`). For example, a `debug` build might include logging and debugging tools, while a `release` build is optimized for performance and size.



### Why is Gradle Important?

  * **Automation** : Automates repetitive build tasks, saving time and reducing errors.
  * **Flexibility** : Highly configurable, allowing you to customize almost every aspect of the build process.
  * **Dependency Management** : Simplifies the inclusion and management of external libraries.
  * **Build Variants** : Enables the creation of multiple app versions from a single project, useful for different environments or monetization strategies.



Understanding Gradle is essential for any Android developer, as it underpins the entire build process. While Android Studio handles much of the complexity, knowing the basics empowers you to troubleshoot build issues, manage dependencies effectively, and customize your build process [3].

## Activities: The Building Blocks of Your App Screens

In Android development, an `Activity` is a fundamental component that represents a single screen with a user interface. Think of an Activity as a single page or view in a web application. When you navigate between different parts of an Android app, you are often switching between different Activities. Unlike traditional programming where an application starts with a `main()` method, the Android system initiates code in an `Activity` instance by invoking specific callback methods that correspond to its lifecycle stages.

### Key Characteristics of Activities:

  * **User Interface** : An Activity provides the window in which your app draws its UI. This window typically fills the screen, but it can also be smaller and float on top of other windows.
  * **Entry Point** : An Activity serves as the primary entry point for user interaction with your app. When one app invokes another, it typically invokes an Activity in the other app, rather than the entire application.
  * **Multiple Activities** : Most Android applications consist of multiple Activities, each responsible for a different screen or task. For example, a messaging app might have one Activity for displaying a list of conversations, another for viewing a single conversation, and yet another for composing a new message.
  * **Main Activity** : Typically, one Activity in an app is designated as the “main” Activity. This is the first screen the user sees when they launch the app from the device’s home screen.
  * **Loose Coupling** : While Activities work together to form a cohesive user experience, they are generally loosely coupled. This means there are minimal dependencies between them, and Activities can even start Activities belonging to other applications.



### The Activity Lifecycle:

An Activity goes through various states during its lifetime, from creation to destruction. The Android system manages these states, and you, as the developer, can respond to these state changes by overriding specific callback methods. Understanding the Activity lifecycle is crucial for managing your app’s resources and ensuring a smooth user experience. The main lifecycle callbacks include:

  * **`onCreate()`** : This is the first callback method invoked when the Activity is created. It’s where you perform basic application startup logic that should happen only once for the entire life of the Activity. This is typically where you set up your user interface (e.g., `setContentView(R.layout.activity_main)`).
  * **`onStart()`** : Called when the Activity becomes visible to the user. This is where you might start animations or begin updating UI elements.
  * **`onResume()`** : Called when the Activity starts interacting with the user. This is the state where the Activity is at the top of the Activity stack and is receiving user input. This is where you should enable any functionality that needs to be active only when the user is actively interacting with the app.
  * **`onPause()`** : Called when the system is about to resume a previous Activity or when another Activity is coming into the foreground. This is where you should pause operations that should not continue while the Activity is in the background, such as animations or video playback. You should also save any persistent data here.
  * **`onStop()`** : Called when the Activity is no longer visible to the user. This might happen if another Activity has completely covered it, or if the Activity is being destroyed. You should release almost all resources here.
  * **`onRestart()`** : Called when the Activity is stopped and is about to be restarted. This occurs when the user navigates back to the Activity after it has been stopped.
  * **`onDestroy()`** : The final callback before the Activity is destroyed. This is where you should release all remaining resources that were allocated in `onCreate()` or other lifecycle methods.



### Declaring Activities in the Manifest:

For the Android system to recognize and launch your Activities, you must declare them in your `AndroidManifest.xml` file within the `` element using the `` tag. The `android:name` attribute specifies the class name of your Activity. You can also define other attributes like `android:label` (the title displayed to the user) and `android:icon` (the icon for the Activity).

```
<activity
        android:name=".MainActivity"
        android:label="@string/app_name"
        android:exported="true">
        <intent-filter>
            <action android:name="android.intent.action.MAIN" />
            <category android:name="android.intent.category.LAUNCHER" />
        intent-filter>
    activity>
    

```
In this example, `MainActivity` is declared. The `android:exported="true"` attribute makes the activity available to other apps. The `intent-filter` with `android.intent.action.MAIN` and `android.intent.category.LAUNCHER` indicates that this Activity is the main entry point of the application and should appear in the device’s app launcher.

Understanding Activities and their lifecycle is fundamental to building well-behaved and efficient Android applications. Proper management of the lifecycle ensures that your app behaves correctly when users navigate through it, when other apps interrupt it, and when the device’s configuration changes [4].

## Permissions: Protecting User Privacy

Android permissions are a crucial aspect of the platform, designed to protect user privacy by controlling an app’s access to sensitive data and system features. For developers with a web background, you can think of Android permissions as being analogous to the browser’s permission prompts for things like accessing the user’s location, camera, or microphone. However, Android’s permission system is more extensive, covering a wider range of device capabilities.

### Why are Permissions Necessary?

Permissions are in place to ensure that users have control over their data and that they are aware of what information an app is accessing and why. This helps build user trust and promotes a more secure mobile ecosystem. As a developer, it’s your responsibility to request only the permissions that are essential for your app’s functionality and to be transparent with users about why you need them.

### Types of Permissions:

Android categorizes permissions into several types, each with a different level of protection and user interaction required:

  1. **Install-time Permissions** : These permissions are automatically granted to your app when the user installs it from the Google Play Store. They are considered to have a lower risk to user privacy. Examples include `android.permission.INTERNET` (for accessing the internet) and `android.permission.VIBRATE` (for controlling the device’s vibrator).
  2. **Runtime Permissions (Dangerous Permissions)** : These permissions grant your app access to sensitive user data or system features that can significantly impact user privacy or the device’s operation. These permissions must be requested at runtime, meaning your app must explicitly ask the user for permission while it’s running. The user can grant or deny these permissions, and they can also revoke them at any time from the device’s settings. Examples include `android.permission.CAMERA`, `android.permission.READ_CONTACTS`, and `android.permission.ACCESS_FINE_LOCATION`.
  3. **Special Permissions** : These permissions are for specific, powerful operations that are less common. They are also requested at runtime, but the system directs the user to a special settings screen to grant the permission. An example is `android.permission.SYSTEM_ALERT_WINDOW`, which allows an app to draw on top of other apps.



### The Workflow for Requesting Permissions:

  1. **Declare Permissions in the Manifest** : Before you can request any permission, you must first declare it in your `AndroidManifest.xml` file using the `` element. This informs the system and the user about the permissions your app might request. 

```
name="android.permission.CAMERA" />
         

```
2. **Check for Existing Permissions** : Before requesting a runtime permission, you should always check if the user has already granted it to your app. You can do this using the `ContextCompat.checkSelfPermission()` method.
  3. **Request the Permission** : If the permission has not been granted, you should request it from the user. This is done by calling `ActivityCompat.requestPermissions()`. This will display a system dialog to the user, asking them to grant or deny the permission.
  4. **Handle the Permission Result** : After the user responds to the permission request, your app will receive a callback with the result. You need to override the `onRequestPermissionsResult()` method in your Activity to handle this result and proceed accordingly.



### Best Practices for Permissions:

  * **Request Minimal Permissions** : Only request the permissions that are absolutely necessary for your app’s functionality.
  * **Provide Context** : Before requesting a permission, explain to the user why your app needs it. This helps build trust and increases the likelihood that the user will grant the permission.
  * **Request Permissions in Context** : Request permissions at the moment they are needed, rather than all at once when the app starts. For example, request the camera permission only when the user taps a button to take a photo.
  * **Handle Permission Denial Gracefully** : If the user denies a permission, your app should continue to function, perhaps with reduced functionality. You should also provide a way for the user to grant the permission later if they change their mind.



Understanding and correctly implementing Android’s permission system is essential for creating a secure and user-friendly application. By following best practices and being transparent with users, you can build a positive relationship with your audience and ensure that your app respects their privacy [5].

## Building Your First Android App: A Step-by-Step Tutorial

Now that you have a foundational understanding of Android development concepts, let’s put that knowledge into practice by building your very first Android application. We’ll create a simple “Hello World” app using Android Studio and Kotlin, which will introduce you to the basic workflow of Android development.

### Step 1: Install Android Studio

Android Studio is the official Integrated Development Environment (IDE) for Android app development. It includes everything you need to build Android apps, including a code editor, visual layout editor, debugging tools, and an emulator. If you haven’t already, download and install Android Studio from the official Android Developers website [6]. Follow the installation instructions for your operating system. The installation process might take some time as it downloads necessary SDK components.

### Step 2: Create a New Project

Once Android Studio is installed and launched, you’ll see a welcome screen. Follow these steps to create a new project:

  1. Click on **“New Project”**.
  2. In the “New Project” wizard, select the **“Empty Activity”** template under the “Phone and Tablet” tab. This template provides a minimal starting point for your app.
  3. Click **“Next”**.
  4. Configure your project with the following details: 
     * **Name** : `MyFirstApp` (You can choose any name, but for this tutorial, let’s stick to this.)
     * **Package name** : `com.example.myfirstapp` (This is usually automatically generated based on your app name and company domain. It must be unique.)
     * **Save location** : Choose a directory on your computer where you want to save your project.
     * **Language** : `Kotlin`
     * **Minimum SDK version** : Select an API level. For beginners, it’s generally recommended to choose a recent but not the very latest version to ensure compatibility with a wide range of devices. For example, you can choose **API 21: Android 5.0 (Lollipop)** or higher. This specifies the minimum Android version your app will support.
  5. Click **“Finish”**.



Android Studio will now set up your project, which might take a few moments as it downloads dependencies and indexes files. Once it’s ready, you’ll see the main IDE window with your project files.

### Step 3: Explore the Project Structure

Android Studio organizes your project files in a specific structure. Here are some key directories and files you’ll encounter:

  * **`app/`** : This is the main module for your application. Most of your app’s code and resources will reside here. 
    * **`src/main/java/com/example/myfirstapp/`** : This directory contains your Kotlin source code files. You’ll find `MainActivity.kt` here, which is the main Activity file generated by the template.
    * **`src/main/res/`** : This directory contains all your app’s resources, such as layouts, images, and strings. 
      * **`layout/`** : Contains XML files that define your app’s user interface layouts (e.g., `activity_main.xml`).
      * **`mipmap/`** : Contains your app’s launcher icons.
      * **`values/`** : Contains XML files for various values like strings (`strings.xml`), colors (`colors.xml`), and themes (`themes.xml`).
    * **`AndroidManifest.xml`** : As discussed earlier, this file declares the essential characteristics of your app.
    * **`build.gradle.kts (Module: app)`** : This is the module-level Gradle build file where you configure dependencies, build types, and other module-specific settings.
  * **`Gradle Scripts/`** : This section in the Project window lists all the Gradle build files in your project. 
    * **`build.gradle.kts (Project: MyFirstApp)`** : The project-level Gradle build file.



### Step 4: Understand `MainActivity.kt` and `activity_main.xml`

When you open `MainActivity.kt`, you’ll see something like this:

```
package com.example.myfirstapp
    
    import android.os.Bundle
    import androidx.activity.ComponentActivity
    import androidx.activity.compose.setContent
    import androidx.compose.foundation.layout.fillMaxSize
    import androidx.compose.material3.MaterialTheme
    import androidx.compose.material3.Surface
    import androidx.compose.material3.Text
    import androidx.compose.runtime.Composable
    import androidx.compose.ui.Modifier
    import androidx.compose.ui.tooling.preview.Preview
    import com.example.myfirstapp.ui.theme.MyFirstAppTheme
    
    class MainActivity : ComponentActivity() {
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContent {
                MyFirstAppTheme {
                    // A surface container using the 'background' color from the theme
                    Surface(
                        modifier = Modifier.fillMaxSize(),
                        color = MaterialTheme.colorScheme.background
                    ) {
                        Greeting("Android")
                    }
                }
            }
        }
    }
    
    @Composable
    fun Greeting(name: String, modifier: Modifier = Modifier) {
        Text(
            text = "Hello $name!",
            modifier = modifier
        )
    }
    
    @Preview(showBackground = true)
    @Composable
    fun GreetingPreview() {
        MyFirstAppTheme {
            Greeting("Android")
        }
    }
    

```
Let’s break down the key parts:

  * **`package com.example.myfirstapp`** : Declares the package name for this file.
  * **`import` statements**: These lines import necessary classes and functions from the Android SDK and Jetpack Compose libraries.
  * **`class MainActivity : ComponentActivity()`** : This defines your `MainActivity` class, which inherits from `ComponentActivity`. `ComponentActivity` is a base class for activities that use Jetpack Compose.
  * **`override fun onCreate(savedInstanceState: Bundle?)`** : This is the `onCreate()` lifecycle method we discussed earlier. It’s the entry point for your Activity. Inside this method: 
    * `super.onCreate(savedInstanceState)`: Calls the `onCreate()` method of the parent class.
    * `setContent { ... }`: This is a Jetpack Compose function that sets the content of your activity. The UI is defined within the lambda passed to `setContent`.
  * **`@Composable fun Greeting(name: String, modifier: Modifier = Modifier)`** : This is a `@Composable` function. In Jetpack Compose, UI elements are built using composable functions. This `Greeting` function takes a `name` and displays “Hello [name]!” using a `Text` composable.
  * **`@Preview(showBackground = true) @Composable fun GreetingPreview()`** : This is a preview function that allows you to see how your composable looks directly in Android Studio without running the app on a device or emulator.



Now, let’s look at `activity_main.xml` (if you chose an Empty Activity template that uses XML layouts, otherwise, the UI is defined directly in Kotlin with Compose). If you chose the Empty Activity with Compose, you won’t have an `activity_main.xml` for the UI itself, as Compose builds UI programmatically. However, you might still have `res/layout/activity_main.xml` if you selected a template that mixes Compose with traditional Views, or if you’re looking at an older project. For a pure Compose project, the UI is entirely in Kotlin.

### Step 5: Run Your App

To see your app in action, you can run it on an Android emulator or a physical Android device.

#### Running on an Emulator:

  1. In Android Studio, locate the **“Device Manager”** icon in the toolbar (it looks like a small phone with a play button). Click it to open the Device Manager.
  2. If you don’t have any virtual devices set up, click **“Create device”**.
  3. Choose a hardware profile (e.g., Pixel 6) and click **“Next”**.
  4. Select a system image (Android version) to download. Choose a stable release (e.g., “API 30” or “API 31”). Click **“Download”** next to the desired system image and then **“Next”**.
  5. Configure the AVD (Android Virtual Device) name and other settings, then click **“Finish”**.
  6. Once your virtual device is created, you can select it from the dropdown menu in the Android Studio toolbar (next to the green play button).
  7. Click the **“Run ‘app'”** (green play) button in the toolbar. Android Studio will build your app and launch it on the selected emulator.



#### Running on a Physical Device:

  1. **Enable Developer Options on your Android device** : Go to `Settings > About phone` and tap “Build number” seven times. You’ll see a message that “You are now a developer!”
  2. **Enable USB Debugging** : Go to `Settings > System > Developer options` and enable “USB debugging.”
  3. **Connect your device** : Connect your Android device to your computer using a USB cable.
  4. **Allow USB Debugging** : On your device, you’ll see a prompt asking to “Allow USB debugging.” Tap “OK.”
  5. **Select your device** : In Android Studio, your connected device should appear in the device dropdown menu in the toolbar.
  6. Click the **“Run ‘app'”** (green play) button. Android Studio will install and launch your app on your physical device.



You should now see “Hello Android!” displayed on your emulator or physical device screen. Congratulations, you’ve just built and run your first Android app!

### Next Steps:

Now that you have a basic app running, you can start experimenting:

  * **Change the text** : Modify the `Greeting` composable in `MainActivity.kt` to display a different message.
  * **Add more UI elements** : Explore other Jetpack Compose composables like `Button`, `Image`, `Column`, `Row`, etc., to add more elements to your UI.
  * **Learn more Kotlin** : Continue practicing Kotlin fundamentals. The official Kotlin documentation and the Android Basics with Compose course are excellent resources.



This hands-on experience is crucial for solidifying your understanding of Android development. Keep experimenting and building, and you’ll quickly become more comfortable with the platform [7].

## References

[1] Android Developers. _Android Basics with Compose_. Available at: <https://developer.android.com/kotlin/androidbasics>

[2] Android Developers. _App manifest overview_. Available at: <https://developer.android.com/guide/topics/manifest/manifest-intro>

[3] Android Developers. _Gradle build overview_. Available at: <https://developer.android.com/build/gradle-build-overview>

[4] Android Developers. _Introduction to activities_. Available at: <https://developer.android.com/guide/components/activities/intro-activities>

[5] Android Developers. _Permissions on Android_. Available at: <https://developer.android.com/guide/topics/permissions/overview>

[6] Android Developers. _Download Android Studio_. Available at: <https://developer.android.com/studio>

[7] Android Developers. _Run your app_. Available at: <https://developer.android.com/studio/run>