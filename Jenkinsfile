pipeline {
    agent any
    tools {
        maven "Maven3"
        jdk "OracleJDK8"
    }


    environment {
        SNAP_REPO = "vprofile-snapshot"
        NEXUS_USER = "admin"
        NEXUS_PASS = "admin123"
        RELEASE_REPO = "vprofile-release"
	    CENTRAL_REPO = "vpro-maven-central"
        NEXUSIP = "172.31.26.8"
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
        SONARSERVER = 'sonarserver'
        SONARSCANNA = 'sonarscanner'
      
    }

    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }

            post {
                success {
                    echo "Now Archiving"
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }

        stage('TEST'){
            steps {
                sh 'mvn -s settings.xml test'
            }
        }

        stage ('CODE ANALYSIS WITH CHECKSTYLE'){
            steps {
                sh 'mvn -s settings.xml checkstyle:checkstyle'
            }
        }


        stage('Sonar Analysis') {
            environment{
                scannerHome = tool "${SONARSCANNER}"

stage('TEST'){
            steps {
                sh 'mvn -s settings.xml test'
            }
    }

    stage ('CODE ANALYSIS WITH CHECKSTYLE'){
            steps {
                sh 'mvn -s settings.xml checkstyle:checkstyle'
            }
        }
    }

}
