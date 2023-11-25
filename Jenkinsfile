pipeline {
    agent {node { label 'agent1' } }
    options{
        ansiColor('xterm')
        timeout(time: 5, unit: 'MINUTES')
    }
    environment {
        NAME = "PEDDIREDDY HARI VARDHAN REDDY"
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                npm install
                echo "Installing Dependencies"
                echo "My name is $NAME"
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
        stage('publish artifact') {
            steps {
                nexusArtifactUploader(
                nexusVersion: 'nexus3',
                protocol: 'http',
                nexusUrl: '54.159.107.80:8081/',
                groupId: 'com.roboshop',
                version: '1.0.1',
                repository: 'catalogue',
                credentialsId: 'nexus-auth',
                artifacts: [
                    [artifactId: 'catalogue',
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
                    echo "Deploying the code is completed"
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

 // first checkout the repository 
 // unit testing 
 // integration testing
 // then scanning the code using sonar cube 
 // build the code and push the artifact repository

 // lauch template 
 // target group
 // autoscaling
 // policy
 // listener


