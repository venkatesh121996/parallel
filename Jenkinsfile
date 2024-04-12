pipeline {
    agent any
    stages {
        stage('Image') {
            steps {
                agent {
                    DOCKER {
                        image 'httpd'
                    }
                }
            }
        }
        stage ('Container') {
            steps {
                sh 'sudo docker run -d -p 3023:80 httpd'
            }
        }
        stage('Parallel Stage') {
            parallel {
                stage('Container A') {
                    steps {
                        sh 'sudo docker run -d -p 3021:80 httpd'
                    }
                }
                stage('Container B') {
                    steps {
                        sh 'sudo docker run -d -p 3020:80 nginx'
                    }
                }
            }
        }
    }
}
