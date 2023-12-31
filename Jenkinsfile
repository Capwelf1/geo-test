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
                sh 'curl --upload-file target/bioMedical-0.02-SNAPSHOT.jar -u admin:devops -v http://ec2-54-166-112-199.compute-1.amazonaws.com:8081/repository/del-repo/'
            }

        }
    }       
          
}