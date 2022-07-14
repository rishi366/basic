pipeline {
    agent any 
    stages {
 
		stage('Git-Checkout'){
			steps {
                echo "Git checkout is onn"
                withCredentials([gitUsernamePassword(credentialsId: 'my-access-jenkins-token',
                 gitToolName: 'git-tool')]) {
                 sh 'git fetch --all'
                }
            }
	    }
        			
        stage('Build') { 
            steps {
                echo "Build is in process"
                sh 'scripts/build.sh'
            }
        }
        stage('Test') { 
            steps {
                echo "Test Successfully"
                sh 'scripts/test.sh'

            }
        }
        stage('Deploy') { 
            steps {
                echo "Deployed Successfully"
                sh 'deploy/build.sh'
              
            }
        }
    }
}
