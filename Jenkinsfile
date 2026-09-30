pipeline {
    agent any

    stages {

        stage('Getting source code from GitHub') {
            steps {
                checkout scm
            }
        }

        stage('Building the project') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Running SonarQube analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat 'mvn sonar:sonar'
                }
            }
        }
    }
}
