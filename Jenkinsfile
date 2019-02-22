pipeline {
    agent any
    stages{
        tools {
            rtMaven.tool = "Maven-3.6.0"
            maven '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/localMaven/bin/'

        }
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}



