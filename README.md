# Profile-jenkins-ci
### This is a demo project showing CI pipline setup and flow.



![Project diagram](images/profile-jenkins-ci.gif)

### Tools  and technologies used

- Jenkins as continues integration server
- Git as version control system
- Maven as build tool
- Checkstyle as code analysis tool
- Sonatype Nexus as artifact/software repo 
- Sonarqube as code analysis server
- AWS EC2 servers for server setup
- Slack for notification

 
> Flow of execution

- Developer makes a commit to SCM (GitHub)
- Jenkins server will automatically fetch the code
- Unit tests will be run.If any failure the notification will be sent to Slack
- If it passes code analysis will be done using Checkstyle and Sonarqube Scanner
- It will generate a report,which we're going to publish on Sonarqube server
- We have Quality Gates.If it passes we will go the next level.
- If not notification will be sent to Slack and the process will be stopped
- Build process will start with Maven (java code)


