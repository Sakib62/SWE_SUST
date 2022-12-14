<h1 align="center">Android App Development</h1>

<h2>Resource:</h2>

- [Introduction to Gradle](https://static.studytonight.com/android/images/introduction-to-gradle.png)

- [Android Developer](http://developers.android.com/)

- [Github Collaboration Guide](https://medium.com/@jonathanmines/the-ultimate-github-collaboration-guide-df816e98fb67)

- [Collaborating With Git](https://vickysteeves.gitlab.io/collaborating-with-git/collaborating-with-git.html)


<details><summary><h2>Lecture-01: 25th August, 2022</h2></summary>

- Android App with Java or Kotlin or framework
- Database - Firebase
- Install Android Studio. Use emulator or install the app in phone for testing
- Maintain in git repo.

<br>

- First try with basic app with some page. 
- Experiment with intent switching, button, layout etc.
- Then try Database.

</details>

<details><summary><h2>Lecture-02: 15th September, 2022</h2></summary>

- Demo with Android Studio.
- Creating new project.
- File Structure. Gradle Build.

**Android File Structure**
- app
    - manifest
    - java
    - res
- gradle scripts

<br>
<h2>APP</h2>

**1. Manifest files**
- one of the important sections. All activity of app, component, permission.<br>
`<application android:label="EmptyActivity" tools:targetApi="31"...../>`

**2. Java**
- logical file

**3. Res folder**
- drawable (static images that will be used in app)
- layout (design code of UI, can be auto-generated via drag & drop)
- mipmap (icon size proportion with respect to screen size)
- values 
    - color (a color code can be given a name to use later)
    - dimens
    - strings (name of static page/segment used statically. If changed here, applied everywhere.)
- xml

<br>

<h2>Gradle</h2>

- a build system responsible for compilation, testing, deployment and code conversion to .dex file.
<br>It is not a compiler though.
- Gradle is in project/modular level & in applicaiton level(applied to all sub module/subproject).
- build.gralde file twice. once in app, another in gradle. Viewed in project file section.

In modular gradle, dependencies are specified that is third party library to be used in the project. defaultConfig is specified.

<img src="https://static.studytonight.com/android/images/introduction-to-gradle.png"/>

Emulator 
- loading first time will take time
- then after modifying code, run in emulator. This time it doesn't take much time.

Activity
- to run, at least one/default activity is needed as starting point. `Activity denotes template of the page.`
- launcher activity only one. It triggers initial activity.
- against each activity, a layout file(.xml) will be generated.
- AndroidManifest.xml will identify each activity. <br>Apk recognize activities that are in manifest file.

</details>

<details><summary><h2>Lecture-03: 22th September, 2022</h2></summary>

</details>

