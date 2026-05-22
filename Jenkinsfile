pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/ManojKumar8244/java-ci-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }

    }
}