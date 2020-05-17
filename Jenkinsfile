pipeline {
	agent any
	stages {
	    stage('Connection') {
	        steps {
	            git 'https://github.com/anu1231/BatchFiles_Pipelines.git'
	            echo "connection successful"
	        }
	    }
	  stage('compile') {
	   steps {
	       bat label: '', script: 'First.bat'
		   echo "compiled Successfully";
		}
	}
	  stage('Running') {
	    steps {
	        bat label: '', script: 'second.bat'
		    echo "run successful";
		}
        }
    }

        post {
	      always {
                  echo 'This will always run'
		}
		success {
		   echo 'This will run only if successful'
		}
		failure {
		   echo 'This will run only if failed'
		}
		unstable {
		   echo 'This will run only if the run was marked as unstable'
		}
		changed {
		   echo ' This will run only if the state of pipeline has changed'
		   echo ' For example, if the pipeline was previousle failed but is now successful'
		}
		
	}
}
