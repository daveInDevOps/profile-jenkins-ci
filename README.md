# Profile-jenkins-ci
### This is a demo project showing CI pipline setup and flow.



![Project diagram](images/profile-jenkins-ci.gif)

### Tools  and technologies used

- Jenkins as continues integration server
- Git as version control system
- Maven as build tool
- Checkstyle as code analysis tool
- Sonatype Nexus as artifact/software repository 
- Sonarqube as code analysis server
- AWS EC2 servers for server setup
- Slack for notifications

 
> Flow of execution

- Developer makes a commit to SCM (GitHub)
- Jenkins server will automatically fetch the code
- Unit tests will be run.If any failure > Slack notification
- If it passes code analysis will be done using Checkstyle and Sonarqube Scanner
- It will generate a report,which we're going to publish on Sonarqube server
- We have Quality Gates.If it passes we will go the next level.If failure > Slack notification
- Build process will start with Maven (java code).If failure > Slack notification
- Maven dependencies we have gone store in Nexus repository
- Once we have artifact we're going to upload a new version back to Nexus server


> Provisioning

- Project source code > src/main
- Unit tests > src/tests
- Jenkins Pipelines > Jenkinsfile
- Jenkins setup > userdata/jenkins-setup.sh
- Nexus setup > userdata/nexus-setup.sh
- Sonar > userdata/sonar-analysis-properties
- Sonar setup > userdata/sonar-setup.sh



