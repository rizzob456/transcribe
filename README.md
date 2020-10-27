 Install Gradle (optionally Maven) and Java8
 Clone the repo 
 Create a user in WorkMail assign an email address like user@abc.awsapps.com
 Create a Lambda function (from the code EmailProcessorLambda.py) with Python 3.8 Runtime
 Modify S3BucketName and DynamoRegion properties in the function accordingly
 Assign S3, DynamoDB and WorkMail permissions to the role used by this lambda function
 Create a rule by going to WorkMail console -> Organization Settings -> Inbound Rules and setting Action to Run Lambda and specifying name of Lambda function created in earlier step and specify domain/email address for the filtering
 In the project directory update BUCKET_NAME variable inside 1-create-bucket.sh script
 Update Constants.java file accordingly 
 Update template.yml file (s3 bucket name etc.)
 Execute 1-create-bucket.sh
 Execute 2-build-layer.sh
 Execute 3-deploy.sh
 Confirm if Java Lambda function has been created and S3 event trigger has been configured correctly
 Assign S3, DynamoDB, SES and Transcribe permissions to the role used by this lambda function
 Update Timeout setting of this function to 5 minutes
 Go to SES console and validate email addresses that are going to be used for testing (this is a MUST if the SES account is a Sandbox account) 
 Send an email to the WorkMail inbox with an audio file attachment (WAV/M4A/MP3/MP4) and in the response email - the sender will receive the transcribed file 
