1. Install AWS CLI, Gradle (optionally Maven) and Java8
2. Clone the repo 
3. Create a user in WorkMail assign an email address like user@abc.awsapps.com
4. Create a Lambda function (from the code EmailProcessorLambda.py) with Python 3.8 Runtime
5. Modify S3BucketName and DynamoRegion properties in the function accordingly
6. Assign S3, DynamoDB and WorkMail permissions to the role used by this lambda function
7. Create a rule by going to WorkMail console -> Organization Settings -> Inbound Rules and setting Action to Run Lambda and specifying name of Lambda function created in earlier step and specify domain/email address for the filtering
8. In the project directory update BUCKET_NAME variable inside 1-create-bucket.sh script
9. Update Constants.java file accordingly 
10. Update template.yml file (s3 bucket name etc.)
11. Execute 1-create-bucket.sh
12. Execute 2-build-layer.sh
13. Execute 3-deploy.sh
14. Confirm if Java Lambda function has been created and S3 event trigger has been configured correctly
15. Assign S3, DynamoDB, SES and Transcribe permissions to the role used by this lambda function
16. Update Timeout setting of this function to 5 minutes
17. Go to SES console and validate email addresses that are going to be used for testing (this is a MUST if the SES account is a Sandbox account) 
18. Send an email to the WorkMail inbox with an audio file attachment (WAV/M4A/MP3/MP4) and in the response email - the sender will receive the transcribed file 
