pipeline {
    
    agent any
    
    stages{
        
        stage('checkout clone'){
            steps{
                git branch: 'feature/2026.02.10', credentialsId: 'vickky9494', url: 'https://github.com/vickky9494/spring-petclinic.git'
            }
        }
        stage('Build'){
            steps{
                bat 'mvn install'
            }
        }
        stage('Test'){
           steps{
               bat 'mvn test'
           }
        }
        stage('Generative Junit Tests result'){
            steps{
                junit 'target/surefire-reports/*.xml'
            }
        }
        stage('Gererated the Artifacts'){
            steps{
                archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }
        }
    }
}