An Android app which lets the user build a custom visual and auditory vocabulary, useful for guided anomia treatment and self designed language lessons by heritage speakers.

Plugs into FieldDB databases to create language learning apps.

[![Video shows how heritage speakers can use field methods techniques and a Learn X app to practice with their friends and family.](http://img.youtube.com/vi/nULRWUMUc-I/0.jpg)](https://www.youtube.com/watch?v=nULRWUMUc-I)


Install
You can see what this code base is for by installing this app (which was customized for Kartuli/Georgian heritage speakers).
https://play.google.com/store/apps/details?id=com.github.opensourcefieldlinguistics.fielddb.lessons.georgian


Tablet uses fragments side by side:
![learn_x_tablet](https://f.cloud.github.com/assets/196199/2483261/6c4e6442-b0fe-11e3-93df-e74309100571.png)

Phone uses list:
![learn_x_phone_list](https://f.cloud.github.com/assets/196199/2483266/7cb070b4-b0fe-11e3-9a42-de24f7e1be3f.png)

And a separate detail screen (here with speech recognition showing)
![learn_x_phone_speech_recognition](https://f.cloud.github.com/assets/196199/2483269/837d01f0-b0fe-11e3-8707-748ab9b02022.png)


### Development

Copy the sample constants file

```bash
cp app/src/main/java/com/github/fielddb/lessons/PrivateConstantsSample.java app/src/main/java/com/github/fielddb/lessons/PrivateConstants.java
```

Edit the class to be `PrivateConstants` instead of `PrivateConstantsSample`

```java
public class PrivateConstants {
```

Use the command line (or Android Studio) to build the app:


```bash
export MODULE_DIR=/path/to/where/AndroidFieldDB/is
./gradlew installDebug
```

Create a local.properties file, for example:

```
# This file must *NOT* be checked into Version Control Systems,
# as it contains information specific to your local configuration.
#
# Location of the SDK. This is only used by Gradle.
# For customization when using a Version Control System, please read the
# header note.
#Sun Mar 05 18:21:33 EST 2017
ndk.dir=/Users/username/Library/Android/sdk/ndk-bundle
sdk.dir=/Users/username/Library/Android/sdk
keyPassword=apasswordforyourkeystore
storeFile=/Users/username/path/to/your/keystore
```


### Decoding raw audio

```bash
$ adb pull /sdcard/kartuli-speechrecognition
$ cd testinganonymouskartulispeechrecognition1513871391108-kartuli/audio/
$ ffmpeg -y -f s16le -ar 16k  -i 000000000.raw  -ac 1 000000000.raw.mp3
```

