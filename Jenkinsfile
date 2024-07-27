pipeline {
    agent any

    stages {
        stage('without docker') {
            steps {
                sh '''
                    echo 'Hello World'
                    ls -la
                    touch container-no.txt
                '''
                
            }
        }
        stage('with docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "with the docker"
                    ls -la
                    pwd
                    touch container-yes.txt
                '''
            }
        }
    }
}