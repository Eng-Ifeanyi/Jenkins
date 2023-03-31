pipeline {
    agent any
    tools {
        maven "Maven3"
        jdk "OracleJDK8"
    }


    environment {
        SNAP_REPO = "jenkins-maven-snapshot"
        NEXUS_USER = "admin"
        NEXUS_PASS = "admin"
        RELEASE_REPO = "jenkins-maven-release"
	    CENTRAL_REPO = "jenkins-maven-central-public"
        NEXUSIP = "172.31.26.8"
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'jenkins-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
      
    }

    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }
    }
}

