pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'javac Calculator.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'java -cp . Calculator'
            }
        }

        stage('Deploy') {
            when {
                expression { currentBuild.result == null || currentBuild.result == 'SUCCESS' }
            }
            steps {
                echo 'Deploying application...'
                // your deploy commands here
            }
        }
    }
}
