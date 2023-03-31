# CONTINUOUS INTEGRATION WITH JENKINS

#############
### Services used:

- Git & github

- Jenkins

- Java code plus Maven for building

- Checkstyle for code analysis

- Slack for notification

- Email notification

- Nexus as the repository to store artifact

- Sonarqube  for continuous inspection of code quality
and as well using the scanner to scan my code and publish the code in Sonarqube dashboard

- AWS EC2 server was used

.............................................................................................

### OBJECTIVE

- Fault isolation

- Short MTTR

- Faster turn around time to code changes

- Less disruption

................................................................................................
### FLOW OF EXECUTION


1. Login to AWS console

2. Create key pair


3. Create SG for jenkins, Nexus, Sonarqube


4. Create EC2 instances with userdata  and it will provision Jenkins, Nexus, Sonarqube


5. Post installation


6. Jenkins setup and plugin


7. Nexus setup and repo setup


8. Sonarqube login test


9. Create a github repo and migrate code


10. Build job with Nexus integration


11. Github Webhook


12. Sonarqube server integration stage


13. Artifact upload stage


14. Slack Notification integration with Jenkins



### END RESULT OF THIS PIPELINE

When developers make changes to the source code

- There will  be a trigger 

- It will build the artifact

- Dependencies will be downloaded from Nexus

- Test with Unit Test

- Run code analysis with Checkstyle 

- Sonar Scanner Analysis will be carried out and it will upload all the result to Sonarqube server if all the quality gate are passed and lastly 

- Artifact will be uploaded to NEXUS

- Notification will be send on slack channel whether there is a failure or a successful build.


