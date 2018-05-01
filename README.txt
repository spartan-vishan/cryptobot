Installing and using Flutter:

To install and run Flutter, your development environment must meet these minimum requirements:

    Operating Systems: macOS (64-bit)
    
    Disk Space: 700 MB (does not include disk space for Xcode or Android Studio).
    
    Tools: Flutter depends on these command-line tools: bash, mkdir, rm, git, curl, unzip, which

-- Inital Set Up -- 

1. Download the latest release of the Flutter SDK

2. Extract the file as follows:
   
   $ cd ~/development 
   $ unzip ~/Downloads/flutter_macos_v0.3.1-beta.zip

3. Add the flutter tool to your path:

   $ export PATH=`pwd`/flutter/bin:$PATH

4. Run: $ flutter doctor //this checks for missing dependencies to complete set up

-- Continuing set up for iOS dev -- 

5. Configure Xcode command line tools by running: 
   
   $ sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer

6. Configure the command line for deploying to iOS devices: 
   $ brew update

   $ brew install --HEAD libimobiledevice

   $ brew install ideviceinstaller ios-deploy cocoapods

   $ pod setup

7. Start your app by running: 
   
   $ flutter run




Integrating Firebase:

iOS: Install cocoapods
     - install homebrew
     - open terminal and run:
       	         brew install cocoapods
		 pod setup

Android: install Google Repository
     - To verify that Google Repository is installed:

            Android Studio > Tools > Android > SDK Manager > SDK Tools

     - If it is not already installed, select Google Repository > Apply.

Create a New Firebase Project
       - This is done in the Firebase console inside a browser.

Add platform-specific Firebase configuration information

Configure Firebase for iOS
  1. In Xcode, open ios/Runner.xcworkspace in a terminal window
  
  2. Click Runner and copy the string value in the Bundle ID field
  
  3. In the Firebase console, open your Firebase project, then click Add Firebase to your iOS app.
  
  4. In the iOS bundle ID field, specify the string value you copied from step 2. Then click Register App.
  
  5. Drag the generated Info.plist file to the Runner directory of your Runner project in Xcode


Integrate the FlutterFire package

Using plugins for Android development requires editing build.gradle files and adding the plugins to pubspec.yaml. 
For iOS development, only the pubspec.yaml changes are needed.
	  
 1. Add rules to your root-level build.gradle file, to include the google-services plugin.

 buildscript {
    repositories {
       jcenter()
       maven {
       url "https://maven.google.com"
      }
    }

    dependencies {
      classpath 'com.android.tools.build:gradle:2.3.3'
      classpath 'com.google.gms:google-services:3.1.0'              //new
    } 
 } 

 2. Add the apply plugin for Google Services to the end of your app-level build.gradle file (/android/app/build.gradle).

apply plugin: 'com.google.gms.google-services'                        //new


Editing pubspec.yaml

 1. Add the plugins you need for this codelab to the pubspec.yaml in your Flutter project file as follows:

  dependencies:
  flutter:
    sdk: flutter
  image_picker: 0.1.1                                             # new
  google_sign_in: 0.3.1                                           # new
  firebase_analytics: 0.0.4                                       # new
  firebase_auth: 0.2.0                                            # new
  firebase_database: 0.0.12                                       # new
  firebase_storage: 0.0.5                                         # new
