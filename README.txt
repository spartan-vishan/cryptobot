Installing and using Flutter:

To install and run Flutter, your development environment must meet these minimum requirements:

    Operating Systems: macOS (64-bit)
    Disk Space: 700 MB (does not include disk space for Xcode or Android Studio).
    Tools: Flutter depends on these command-line tools being available in your environment: bash, mkdir, rm, git, curl, unzip, which

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

