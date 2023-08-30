pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }

    environment {
        SNAP_REPO = 'vprofile_snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'admin'
        RELEASE_REPO = 'vprofile_release'
        CENTRAL_REPO = 'vpro_maven_central'
        NEXUSIP = '172.31.52.237'
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vpro_maven_group'
        NEXUS_LOGIN = 'nexuslogin'


    }

    stages {
        stage('Build'){
            steps {
               sh 'mvn -s settings.xml clean install -DskipTests' 
            }
        }
    }
}