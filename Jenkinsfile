pipeline {
    agent any

    stages {
        stage('Install dependencies') {
            steps {
                script {
                    if (!fileExists('node_modules')) {
                        sh 'npm install'
                    }
                }
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test -- --watchAll=false'
            }
        }
    }

    post {
        success {
            echo 'Tests passed!'
        }
        failure {
            echo 'Tests failed.'
        }
    }
}
