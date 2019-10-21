pipeline {
    agent none
    
	stages {
	
        stage('Git') {
			agent {
				node { label 'git' }
			}
            steps { git 'https://github.com/RAMSHANKARMCA08/hippo-app-multi.git' }
        }// stage git ends
	
	
	stage('Build') {
			agent {
				node { label 'maven' }
			}
		steps {  
			dir("/var/lib/jenkins/workspace/${JOB_NAME}") {
			sh "docker run -it --rm --name "MyMaven" -v $(pwd):/usr/src/mymaven -w /usr/src/mymaven maven mvn clean install"
       			//archiveArtifacts '**/target/*.war'			
			}			
			}//steps Build ends
			
		}//stage Build ends
	}//stages ends
	}//pipeline ends
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
            deleteDir() // clean up workspace
        }
    }//post ends //next line pipeline ends
