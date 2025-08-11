@Library('github-api-global-lib') _

pipeline {
    agent {
        docker {
            image 'maven:3.9-eclipse-temurin-24'
        }
    }
    
    stages {
        stage('Checkout') {
           steps {
               sh 'ls -l'
           }
        }
         
        stage('Test sharelib') {
            steps {
                helloWorldSimple("JUNJAP", "Monday")
            }

        }
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }        
    }
}
