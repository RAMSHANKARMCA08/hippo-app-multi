pipeline {
    agent none
    environment {
        DISABLE_AUTH = 'true'
	Deployment_Server  = '10.34.56.12'
	AWS_SECRET = credentials('AWS_SECRET')
    		}
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
			//dir("/var/lib/jenkins/workspace/${JOB_NAME}") {
			sh "docker run --rm --name 'MyMaven' -v $pwd/workspace/${JOB_NAME}:/usr/src/mymaven -w /usr/src/mymaven maven mvn clean install"
       			//archiveArtifacts '**/target/*.war'			
			//}			
			}//steps Build ends
			
		}//stage Build ends
		
	stage("Proceed to prod?") {
            agent none
            steps { proceedToDeploy() }
        }
	
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
	
	
	

// =============================================================================
// Initialization steps
// =============================================================================

def initialize() {
	env.BuildEnv = "Prod"
    env.DeployServerIP = "10.0.0.35"
    env.ServerUSerID = "deploy"
	env.ServerUSerID = "deploy"
	}

def proceedToDeploy() {
    def description = "Choose 'yes' if you want to deploy this build"
    def proceed = 'no'
    timeout(time: 10, unit: 'MINUTES') {
        proceed = input message: "Do you want to deploy the changes?",
            parameters: [choice(name: "Deploy Code ", choices: "no\nyes",
                description: description)]
        if (proceed == 'no') {
            error("User stopped pipeline execution")
        }
    }
}

