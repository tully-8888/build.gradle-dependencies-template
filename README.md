# build.gradle-dependencies-template
 Personal choice of Android dependencies and other stuff.

## build.gradle - app

```groovy

//plugins
id 'com.android.application'
    id 'org.jetbrains.kotlin.android'
    id 'dagger.hilt.android.plugin'
    id 'kotlin-kapt'
    id 'androidx.navigation.safeargs.kotlin'
    id("kotlin-parcelize")

// default config
resConfigs "en"

// buildTypes
minifyEnabled false
shrinkResources false

// options
compileOptions {
    sourceCompatibility JavaVersion.VERSION_17
    targetCompatibility JavaVersion.VERSION_17
}
kotlinOptions {
    jvmTarget = JavaVersion.VERSION_17
}

// viewbinding
buildFeatures {
    viewBinding true
}

//kapt
kapt {
    correctErrorTypes true
    useBuildCache true
}

//hilt
hilt {
    enableAggregatingTask = true
    enableExperimentalClasspathAggregation = true
}

//dependencies
///Default
    implementation "androidx.core:core-ktx:1.10.1"
    implementation 'com.google.android.material:material:1.9.0'
    implementation "androidx.constraintlayout:constraintlayout:2.1.4"
    implementation 'androidx.appcompat:appcompat:1.6.1'

    ///Dagger Hilt --- Dependency Injection
    implementation 'com.google.dagger:hilt-android:2.45'
    kapt 'com.google.dagger:hilt-android:2.45'
    kapt 'com.google.dagger:hilt-android-compiler:2.45'

    ///Navigation --- Navigate through fragments
    implementation 'androidx.navigation:navigation-fragment-ktx:2.6.0'
    implementation 'androidx.navigation:navigation-ui-ktx:2.6.0'

    ///Retrofit --- APIs
    implementation 'com.squareup.retrofit2:retrofit:2.9.0'
    implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
    implementation 'com.squareup.okhttp3:logging-interceptor:5.0.0-alpha.9'

    ///ViewBinding
    implementation 'com.github.kirich1409:viewbindingpropertydelegate-noreflection:1.5.8'

    ///Room --- Advanced Local Data Persistence
    implementation "androidx.room:room-runtime:2.5.1"
    implementation 'androidx.room:room-ktx:2.5.1'
    kapt 'androidx.room:room-compiler:2.5.1'

    ///Lifecycle/ViewModel/Coroutines
    implementation 'androidx.lifecycle:lifecycle-viewmodel-ktx:2.6.1'
    implementation 'org.jetbrains.kotlinx:kotlinx-coroutines-android:1.6.4'
    implementation 'androidx.lifecycle:lifecycle-runtime-ktx:2.6.1'
    implementation 'androidx.lifecycle:lifecycle-livedata-ktx:2.6.1'

    ///Data storage
    implementation 'com.github.akshay2211:stash:master'

    ///Coil
    implementation 'io.coil-kt:coil:2.2.2' ```groovy

## build.gradle - project

//at the top
buildscript {
    ext {
        kotlin_version = 'x'
    }
    dependencies {
        classpath 'androidx.navigation:navigation-safe-args-gradle-plugin:2.5.3'
        classpath 'com.android.tools.build:gradle:8.2.0-alpha10'
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
    }
    repositories {
        google()
        mavenCentral()
    }
}

// plugins
id 'com.google.dagger.hilt.android' version '2.45' apply false

