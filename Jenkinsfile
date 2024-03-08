pipeline {
	agent any
	stages {
		stage('Clone repository') {
			steps {
				checkout([$class: 'GitSCM',
				branches: [[name: '*/main']],
				userRemoteConfigs: [[url: 'https://github.com/Shogunkayo/PES1UG21CS206_Jenkins.git']]])
			}
		}
		stage('Build') {
			steps {
				build 'PES1UG21CS206-1'
				sh 'g++ main.cpp -o output'
			}
		}
		stage('Test') {
			steps {
				sh './output'
			}
		}
		stage('Deploy') {
			steps {
				echo 'deploy'
			}
		}
	}
	post {
		failure {
			error 'Pipeline failed'
		}
	}
}
