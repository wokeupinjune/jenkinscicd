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
		git branch: 'master', credentialsId: 'github', url: 'https://github.com/wokeupinjune/dockerdemo'
		dockerImage = docker.build("demo/demo:latest")
        	}
	}
	stage('Push image') {
	    steps {
		sh 'docker image tag demo/demo:latest registry-demo:5000/demo/demo:latest'
		sh 'docker push registry-demo:5000/demo/demo:latest' 	
	    }
   	}
    }
}

