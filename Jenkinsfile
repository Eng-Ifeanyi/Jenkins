pipeline {
    agent any
    tools {
        maven "Maven3"
        jdk "OracleJDK8"
    }


    environment {
        SNAP_REPO = "vprofile-snapshot"
        NEXUS_USER = "admin"
        NEXUS_PASS = "Plaza308"
        RELEASE_REPO = "vprofile-release"
	    CENTRAL_REPO = "vpro-maven-central"
        NEXUSIP = "18.237.139.149"
        NEXUSPORT = '8081'
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
    }
}