pipeline{
    agent any
    tools{
        maven 'M2_HOME'
    }
    stages{
        stage("maven clean"){
            steps{
                sh 'mvn clean'
            }
        }
        stage('maven install '){
            steps{
                sh 'mvn install'
            }
        }
        stage('maven package '){
            steps{
                sh 'mvn package'
            }
        }
        stage('upload artifact'){
            steps{

            nexusArtifactUploader artifacts: [[artifactId: 'bioMedical', 
            classifier: '', file: 'target/bioMedical-0.0.2-SNAPSHOT.jar',
             type: 'jar']], credentialsId: 'NEXUSID', groupId: 'QA', 
             nexusUrl: '54-166-112-199:8081', 
             nexusVersion: 'nexus3', protocol: 'http', repository: 'del-repo', 
             version: '0.0.2-SNAPSHOT'

        }   }
    }       
          
}