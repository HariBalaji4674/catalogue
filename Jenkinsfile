pipeline {
    agent {node { label 'agent1' } }
    options{
        ansiColor('xterm')
        timeout(time: 1, unit: 'HOURS')
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                    echo "peddireddy hari Vardhan reddy"
                '''
            }
        }
        stage('Sonar Scan') {
            steps{
                sh 'ls -ltr'
                //sh 'sonar-scanner'
            }
        }
        stage('Example Test') {
            steps {
                echo 'java -version'
                echo 'peddireddy hari vardhan reddy'
            }
        }
    }
}

// Shift left in devops --> Languages java 