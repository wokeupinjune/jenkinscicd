pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'            }
        }
        stage('git checkout') {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/wokeupinjune/jenkinscicd'
            }
        }
    }
}   
