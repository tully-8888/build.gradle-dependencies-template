# build.gradle-dependencies-template
Personal choice of Android dependencies and other stuff.


## build.gradle - app
### default config
 resConfigs "en"
### buildTypes
minifyEnabled false
shrinkResources false
### options
compileOptions {
        sourceCompatibility JavaVersion.VERSION_17
        targetCompatibility JavaVersion.VERSION_17
    }
    kotlinOptions {
        jvmTarget = JavaVersion.VERSION_17
    }
#viewbinding
 buildFeatures {
        viewBinding true
    }

## build.gradle - project
