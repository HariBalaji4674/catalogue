pipeline {
    agent {node { label 'agent1' } }
    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                    echo "peddireddy hari Vardhan reddy"
                '''
            }
        }
        stage('Unit Testing') {
            steps {
                sh '''
                    echo "Unit Testing is Completed"
                '''
            }
        }
        stage('Sonar Scan') {
            steps{
                sh 'ls -ltr'
                sh 'sonar-scanner'
                sh 'ls -l'
            }
        }
     }
 }

// Shift left in devops --> Languages java 