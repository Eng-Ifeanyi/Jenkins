pipeline {
    agent any
    tools {
        maven "Maven3"
        jdk "OracleJDK8"
    }


    environment {
        SNAP_REPO = "vprofile-snapshot"
        NEXUS_USER = "admin"
        NEXUS_PASS = "admin5050"
        RELEASE_REPO = "vprofile-release"
	    CENTRAL_REPO = "vpro-maven-central"
        NEXUSIP = "18.237.139.149"
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vprofile-group'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages {
        stage("Build"){
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

        stage("TEST"){
            steps {
                sh 'mvn -s settings.xml test'
            }
        }
    }
}