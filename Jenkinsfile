pipeline {
	agent {
		docker 'node:13'
		label 'akali'
		args '-p 3000:3000'
	}
	stages {
		stage('Build') {
			steps {
				echo "create  my apps from create-react-app"
				sh 'npx create-react-app react-app'
			}
		}
		stage('Test') {
			steps {
				echo "Test my app"
				sh 'cd react-app'
				sh 'npm start & sleep 10'
				input message: 'Click process to continue or Not'
			}
		}
	}
}