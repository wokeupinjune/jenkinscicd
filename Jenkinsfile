pipeline {
    agent any
    stages {
        stage('Welcome-test') {
            steps {
                echo 'Hello World'            }
        }
        stage('Git clone') {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/wokeupinjune/jenkinscicd'
            }
        }
	stage('Build') {
	    steps {
		sh 'docker build . -t demo:latest'
        	}
	}
	stage('Push image') {
	    steps {
		sh 'docker image tag demo:latest localhost:5000/demo:latest'
		sh 'docker push localhost:5000/demo:latest' 	
	    }
   	}
    }
}

