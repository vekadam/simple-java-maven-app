pipeline {
    agent none 

    stages {
        stage('Build and Test') {
            agent {
                docker {
                    image 'maven'
                    args '-v $home/.m2:/root/.m2'
                }
            }
            steps {
                sh 'mvn clean test'
            }
            post {
                always {
                    junit 'target/surefire-reports'
                }
            }
        }
    }
}