# Second Screen Experience  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ![](https://i.imgur.com/GjLN4Wf.png)
## Brief Overview
The Second Screen Experience provides Fire TV users the ability to purchase items they see on screen using another android device. The experience is comprised of two applications: SecondScreenTVApp which is deployed on the FireTV and SecondScreenMobileApp which should be installed on an android phone running SDK version 26 (Oreo) or higher. 

## Technologies Used
* AWS Amplify
* AWS Cognito Users Pool
* AWS S3
* AWS Lambda
* AWS Rekognition
* AWS PA API
* DeepVision

## Setup and Configuration
### SecondScreenTVApp
* Download and unzip the project -> SecondScreenTVApp.zip
* Open the application in Android Studio
* Build APK from studio project
* Connect your development computer to your Fire TV through the Android Debug Bridge
* adb install `<path-to-apk-file>`
* More info on adb and installation: https://developer.amazon.com/docs/fire-tv/installing-and-running-your-app.html
### SecondScreenMobileApp
* Download and unzip the project -> SecondScreenMobileApp.zip
* Open the project in Android Studio and Gradle Sync to install the necessary dependencies.
* Set up your AWS backend
  * We recommend setting up AWS Amplify and using the AWS CLI (more info at https://aws-amplify.github.io/docs/)
  * For authentication use Cognito User Pools (https://docs.aws.amazon.com/cognito/index.html)
  * `$ amplify add auth`
  * For image upload and storage use S3 (https://docs.aws.amazon.com/s3/index.html)
  * `$ amplify add storage`
### PA Lambda
* Download and unzip the project -> palambda.zip
* Replace `"YOUR_***_HERE"` with your API keys/credentials
* Build the project with Maven
* Upload the jar file to AWS Lambda
* Give the lambda function the appropriate permissions
### Rekognition Lambda
* Download and unzip the project -> rekognitionlambda.zip
* Replace `"YOUR_DESTINATION_BUCKET_HERE"` with your S3 bucket path
* Build the project with Maven
* Upload the jar file to AWS Lambda
* Give the lambda function the appropriate permissions
* Configure your S3 bucket which holds image uploads from mobile app (source bucket) to trigger this lambda function
## Notes
To develop with this app you must create two S3 buckets. The first bucket will hold images uploaded from the mobile app via TransferUtility. The second bucket will hold the results returned from rekognition that are subsequently downloaded to the mobile app. The visual search functionality is provided by the DeepVision API which requires the user to create datasets in their system. To do this you must acquire an API key, create datasets, and upload data to those datasets via the PA Lambda function. 
## Contributors
Mica Geldert\
Chance Rebholz\
Isaac Jacobsen\
Aaron Kawahara
