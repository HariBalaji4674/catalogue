pipeline {
    agent {node { label 'agent1' } }
    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                    npm install 
                    echo "peddireddy hari Vardhan reddy"
                '''
            }
        }
        stage('Sonar Scan') {
            steps{
                sh 'ls -ltr'
                sh 'sonar-scanner'
            }
        }
     }
 }

// Shift left in devops --> Languages java 