## Misc files used when developing Android app

### Assumption

* [Android SDK][] is installed at `/opt/android-sdk`
* [Android NDK][] is installed at `/opt/android-ndk`
* [Android Studio][] is installed at `/opt/android-studio`


### `conffiles`

configure files either in user's home directory or `/etc`

### `bin`

* `AndroidStudio`: start [Android Studio][] on CLI
* `gradle`: use gradle from [Android Studio][] as default gradle
    so gradlew is not needed any more!
* `signapk`: signing apk with keystore

### `gradle`

* `Makefile`: simple makefile for Android project that use gradle

### `proguard`

[proguard][] rules for some library

[Android SDK]: https://developer.android.com/sdk/index.html
[Android NDK]: https://developer.android.com/ndk/index.html
[Android Studio]: https://developer.android.com/studio/index.html
[proguard]: http://proguard.sourceforge.net/ "ProGuard"
