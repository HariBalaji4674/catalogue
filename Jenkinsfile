pipeline {
    agent {node { label 'agent1 } }
    options{
        timeout(time: 1, unit: 'HOURS')
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                    npm install

                '''
            }
        }
        stage('Example Test') {
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }
    }
}

// Shift left in devops --> Languages java 