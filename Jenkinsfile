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
                sh 'find . -name "*.xml"'
            }
            post {
                always {
                    junit 'target/surefire-reports'
                }
            }
        }
    }
}