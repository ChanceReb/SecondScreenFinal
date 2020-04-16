# Second Screen Experience![](https://i.imgur.com/GjLN4Wf.png)
## Brief Overview
The Second Screen Experience provides Fire TV users the ability to purchase items they see on screen using another android device. The experience is comprised of two applications: SecondScreenTVApp which is deployed on the FireTV and SecondScreenMobileApp which should be installed on an android phone running SDK version 26 (Oreo) or higher. 

# Technologies Used
* AWS Amplify
* AWS Cognito Users Pool
* AWS S3
* AWS Lambda
* AWS Rekognition
* AWS PA API
* DeepVision

## Setup and Configuration
### SecondScreenTVApp
* Download and unzip the source code -> SecondScreenTVApp.zip
* Open the application in Android Studio
* Build APK from studio project
* Connect your development computer to your Fire TV through the Android Debug Bridge
* adb install `<path-to-apk-file>`
* More info on adb and installation: https://developer.amazon.com/docs/fire-tv/installing-and-running-your-app.html
### SecondScreenMobileApp
* Download and unzip the source code -> SecondScreenMobileApp.zip
* Open the project in Android Studio and Gradle Sync to install the necessary dependencies.
* Set up your AWS backend
  * We recommend setting up AWS Amplify and using the AWS CLI (more info at https://aws-amplify.github.io/docs/)
  * For authentication use Cognito User Pools (https://docs.aws.amazon.com/cognito/index.html)
  * `$ amplify add auth`
  * For storage use S3 (https://docs.aws.amazon.com/s3/index.html)
  * `$ amplify add storage`
### 

## Contributors
Mica Geldert\
Chance Rebholz\
Isaac Jacobsen\
Aaron Kawahara
