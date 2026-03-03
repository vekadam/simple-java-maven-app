pipeline {
    agent {
        docker {
            image 'maven'
            args '-v $home/.m2:/root/.m2'
            }
        }

    stages {
        stage('Build and Test') {
            steps {
                sh 'mvn clean test'
                sh 'find . -name "*.xml"'
                junit '**/target/surefire-reports'
            }
        }
    }
}