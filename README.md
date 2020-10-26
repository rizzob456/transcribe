1. TranscribeCleanPackage

GO HERE -> /Users/ssankm/eclipse-workspace/TranscribeDemo

scp -i ~/Downloads/sanjay.pem target/transcribe-service-0.1.0.jar ec2-user@ec2-52-206-32-98.compute-1.amazonaws.com:/home/ec2-user

ssh -i ~/Downloads/sanjay.pem ec2-user@ec2-52-206-32-98.compute-1.amazonaws.com

java -jar transcribe-service-0.1.0.jar
OR better
nohup java -jar transcribe-service-0.1.0.jar &

4. login to ALB -> https://???

5. delete app shortcuts from the iPhone and recreate again...
6. on the desktop - use Safari to access the URLs (https only -> self signed certificate needs to be imported into IAM through CLI).

For TranscribeStreamDemo::
after ssh cd to TranscribeStreamDemo
and run this command -> ws


 ps aux | grep java
 ps aux | grep ws
 kill -9 <PID> 