pipeline {
    agent any

    stages {
        stage('w/o Docker') {
            steps {
                sh '''
                    echo "Without docker"
                    ls -la
                    touch container-no.txt
                '''
            }
        }
        stage('w Docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "With docker"
                    npm --version
                    ls -la
                    touch container-yes.txt
                '''
            }
        }
    }
}
