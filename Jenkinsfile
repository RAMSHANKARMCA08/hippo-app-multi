def logLocation = "/var/lib/jenkins/workspace/${JOB_NAME}"
def logname = 'log_' + str(datetime.now().strftime('%Y_%m_%d')) + '.log'


pipeline {
    agent any
    
	stages {
	
        stage('Git') {
			agent {
				echo "$logLocation/$logname"
				node { label 'git' }
			}
            steps { git 'https://github.com/RAMSHANKARMCA08/hippo-app-multi.git' }
        }// stage git ends
	
	
	stage('Build') {
			agent {
				node { label 'maven' }
			}
		steps {  
			//dir("/var/lib/jenkins/workspace/${JOB_NAME}") {
			sh "docker run --rm --name 'MyMaven' -v $pwd/workspace/${JOB_NAME}:/usr/src/mymaven -w /usr/src/mymaven maven mvn clean install"
       			//archiveArtifacts '**/target/*.war'			
			//}			
			}//steps Build ends
			
		}//stage Build ends
	}//stages ends


post {  
        success {
            echo 'I succeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things are different...'
        }
		always {
            echo 'Job completed'
            //deleteDir() // clean up workspace
        }

    }//post ends
	}//pipeline ends
