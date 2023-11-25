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
        stage('Build'){
            steps{
                sh '''
                echo "peddireddy Build process is completed"
                ls -ltr
                zip -r catalogue.zip ./* --exclude=.git --exclude=.zip
                '''
            }
        }
        stage('publish artifact'){
            steps {
                sh '''
                    echo "publish to nexus repository"   
                '''
                input "please approve the request"
            }
        }
        stage('Deploy'){
            steps{
                sh '''
                    echo "Deploying the code"
                '''
            }
        }
     }
     post {
        always{
            echo "cleaning up the workspace"
            deleteDir()
        }
     }
 }