## How to setup ?

### 1. Copy Files
-	Copy `config` folder into root folder of project
- 	Copy `checkci.gradle`into module folder. Default `app`

### 2. Edit module `build.gradle`

Open `build.gradle` of module app and edit like below code :

```
...
apply plugin: 'com.android.application'
apply from: "checkci.gradle"
...


```

### 3. Customize your project

#### For Checkstyle
`config/checkstyle/google_checks.xml` : Edit rulers

`config/checkstyle/suppressions.xml` : Edit suppressions

#### For Android Lint
`config/lint/lint` : Edit ignore for issue



## Version

#### Checkstyle

	Version : 1.0.2
	Date : 22/03/2016
	- Disable OverloadMethodsDeclarationOrder
	------------------
	Version : 1.0.1
	Date : 11/03/2016
	- Based on Google Java and Google Android


Are there any errors in these config, please feedback at [https://goo.gl/yOzBx5](https://goo.gl/yOzBx5)

## Upgrade config version

#### MAC

Run script in `config` folder, Open terminal and enter `sh ` and move file `upgradeMacOS.sh` to terminal

```
sh /Users/pham.quy.hai/ProjectsCode/Framgia/framgia-android-ci/config/upgradeMacOS.sh 
```

#### LINUX

Run script in `config` folder, Open terminal and enter `sh ` and move file `upgradeLinuxOS.sh` to terminal

```
sh /Users/pham.quy.hai/ProjectsCode/Framgia/framgia-android-ci/config/upgradeLinuxOS.sh 
```