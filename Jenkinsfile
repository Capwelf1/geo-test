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
             nexusUrl: 'ec2-54-166-112-199.compute-1.amazonaws.com:8081', 
             nexusVersion: 'nexus3', protocol: 'http', repository: 'del-repo', 
             version: '0.0.2-SNAPSHOT'

        }   }
    }       
          
}