
pipeline {
	agent any
	stages {
		stage ('Build') {
		steps {
		   sh 'echo "Hello"'
	           sh '''
		      echo "multiline shell steps"
		      ls -ltr
		      '''
		      }
		   }
		
		stage('Deploy') {
            	steps {
                retry(3) {
                    sh 'echo "./deploy.sh"'
                }
                timeout(time: 3, unit: 'MINUTES') {
                    sh 'echo "Quality.sh"'
                }
            }
        }

   }
}
