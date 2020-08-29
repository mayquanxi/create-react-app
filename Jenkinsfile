pipeline {
	agent {
		docker { 
			image 'node:13'
			label 'akali'
			args '-p 3000:3000'
		}
	}
	stages {
		stage('Build') {
			steps {
				echo "create  my apps from create-react-app"  //create new app from create-react-app
				sh 'npx create-react-app react-app'
			}
		}
		stage('Test') {
			steps {
				echo "Test my app"
				sh 'cd react-app'
				sh 'yarn start & sleep 20'
				input (
				  message: 'Click process for continue or abort to quite pipeline',
				  submitter: 'user01, user02, mayquanxi',  //submitter for user01,user02, mayquanxi and admin have permission for aproves jobs  #need use role-base to set permission for job first
				  submitterParameter: 'user_approves'
				) 
			}
		}
	}
}