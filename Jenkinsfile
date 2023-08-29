pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }

    environment {
        SNAP_REPO = "vprofile-snapshot"
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'ADMIN'
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "172.31.88.22"
        NEXUS_REPOSITORY = "vprofile-release"
        NEXUS_PORT = '8081'
	    //NEXUS_REPOGRP_ID    = "vpro-maven-group"
        NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_CREDENTIAL_ID = "nexuslogin"
        ARTVERSION = "${env.BUILD_ID}"
    }

    stages {
        stage('Build'){
            steps {
               sh 'mvn clean install -DskipTests' 
            }
        }
    }
}