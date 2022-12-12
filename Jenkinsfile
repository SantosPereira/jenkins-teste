pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            agent {
                docker {
                    image 'nginx:latest'
                    args '-p 8080:80'
                }
            }
            steps {
                sh "mv ./index.html /var/"
                echo 'Deploying'
            }
        }
    }
}