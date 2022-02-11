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
               nexusArtifactUploader artifacts: [
                   [
                       artifactId: 'RegisterPage', 
                       classifier: '', 
                       file: 'RegisterPage.jar', 
                       type: 'jar'
                   ]
               ], 
                   credentialsId: '0a5b04a0-ec28-4643-9f95-6641d2637d82', 
                   groupId: 'org.example', 
                   nexusUrl: '3.138.139.63:8081', 
                   nexusVersion: 'nexus3', 
                   protocol: 'http', 
                   repository: 'maven-snapshots', 
                   version: '1.0-SNAPSHOT'
            }
        }
    }
 }
