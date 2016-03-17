## How to setup ?

### 1. Copy `config` folder into root folder of project
### 2. Edit `build.gradle`

Open `build.gradle` of module app and edit like below code :

```
...
apply plugin: 'com.android.application'
apply plugin: 'checkstyle'
...
...
...
android {
...
...
...
lintOptions {
        abortOnError false
        lintConfig file("${project.rootDir}/config/lint/lint.xml")
    }
}

task checkstyle(type: Checkstyle) {
    ignoreFailures = true
    showViolations = true
    configFile file("${project.rootDir}/config/checkstyle/google_checks.xml")
    configProperties.checkstyleSuppressionsPath = file("${project.rootDir}/config/checkstyle/suppressions.xml").absolutePath
    source 'src'
    include '**/*.java'
    exclude '**/gen/**'
    classpath = files()
}

dependencies {
    checkstyle 'com.puppycrawl.tools:checkstyle:6.15'
    ...
    ...
    ...
}

```

### 3. Customize your project

#### For Checkstyle
`config/checkstyle/google_checks.xml` : Edit rulers
`config/checkstyle/suppressions.xml` : Edit suppressions

#### For Android Lint
`config/lint/lint` : Edit ignore for issue



## Version

#### Checkstyle

Framgia checkstyle config

Version : 1.0.1

Date : 11/03/2016

Are there any errors in these config, please feedback at [https://goo.gl/O2CX0D](https://goo.gl/O2CX0D)