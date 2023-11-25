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
        stage('Build'){
            steps{
                sh '''
                ls -ltr
                zip -r catalogue.zip ./* --exclude=.git --exclude=.zip
                '''
            }
        }
        stage('publish artifact'){
            steps{
                nexusArtifactUploader(
                nexusVersion: 'nexus3',
                protocol: 'http',
                nexusUrl: '54.159.107.80:8081/',
                groupId: 'com.roboshop',
                version: '1.0.',
                repository: 'catalogue',
                credentialsId: 'nexus-auth',
                artifacts: [
                    [artifactId: catalogue,
                    classifier: '',
                    file: 'catalogue.zip',
                    type: 'zip']
        ]
     )
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