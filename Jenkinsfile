pipeline {
    agent any
    tools {
         maven 'maven3'
    }
    stages{
        stage('Build'){
            steps{
                  sh script: 'mvn clean package'
            }
        }
        stage('Upload Jar To Nexus'){
            steps{ 
               nexusArtifactUploader artifacts: [[artifactId: 'RegisterPage', classifier: '', file: '/var/lib/jenkins/jobs/pipeline/config.xml', type: 'jar']], credentialsId: '33920a98-cde2-4b60-a627-827bda4a9a64', groupId: 'org.example', nexusUrl: '3.16.128.89:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-snapshots', version: '1.0-SNAPSHOT'
            }
        }
    }
 }
