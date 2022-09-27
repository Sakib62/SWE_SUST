<h1 align="center">Android App Project with Java/Kotlin</h1>

<details><summary><h2>Lecture-01: 25th August, 2022</h2></summary>

Android App with Java or Kotlin.<br>
Database - Firebase<br>
Install Android Studio. Emulator or install the app in phone for testing<br>
Maintain in git repo.

First try with basic app with some page-- intent switching, button, layout etc.<br> Then try Database.

Setup environment in pc.
</details>

<details><summary><h2>Lecture-02: 15th September, 2022</h2></summary>

Demo with Android Studio.

Creating new project.<br>
File Structure. Gradle Build.

Android
- app
    - manifest
    - java
    - res
- gradle scripts
  
manifest files - one of the important. All activity of app, component, permission.<br>
<application android:label="EmptyActivity" tools:targetApi="31"...../>

java te logical file

in res folder
- drawable
- layout
- mipmap
- values
- xml

static img to be used in app is in drawbale

design code of used ui is in layout. Can be auto generated via drag & drop.

icon size proportion with respect to screen size in mipmap

in values folder
- color
- dimens
- strings

in color, a color code code can be given a name to use later

in string, name of static page/segment used statically. If chnaged here, applied everywhere.

Gradle - a build system responsible for compilation, testing, deployment and code conversion to .dex file.
<br>It is not a compiler though.

Gradle is in project/modular level & in applicaiton level(applied to all sub module/subproject). build.gralde file twice. once in app, another in gralde. Viewed in project file section.

In modular gradle, dependencies are specified that is third party library to be used in the project. defaultConfig is specified.

<img src="https://static.studytonight.com/android/images/introduction-to-gradle.png"/>

Emulator loading first time will take time. Then after modifying code, run in emulator. These time it doesn't take much time.

To run, at least one/default activity is needed as starting point. ~Activity denotes template of the page.~

Launcher activity only one. Triggers initial activity.

Against each activity, a layout file(.xml) will be generated.

AndroidManifest.xml will identify each activity. apk recognize activities that are in manifest file.

</details>

<details><summary><h2>Lecture-03: 22th September, 2022</h2></summary>

</details>

