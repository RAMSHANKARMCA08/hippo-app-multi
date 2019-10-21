pipeline {
    agent none
    
	stages {
	
        stage('Git') {
			agent { 
                label 'git'
            }
            steps { git 'https://github.com/RAMSHANKARMCA08/hippo-app-multi.git' }
        }// stage git ends
	
	
	stage('Build') {
	agent { 
                label 'maven'
            }
		steps {  
			dir("/var/lib/docker/volumes/jenkins_home/_data/workspace/hippo-app-multi/") {
			//withDockerContainer(args: '-it --rm --name my-maven-project -v /var/lib/docker/volumes/jenkins_home/_data/workspace/hippo-app-multi -w /var/lib/docker/volumes/jenkins_home/_data/workspace/hippo-app mvn -multi install', image: 'maven') {
   				 echo "Inside Block"
			}
       			// archiveArtifacts '**/target/spring-boot-web-jsp-1.0.war'			
			}			
			}
			
		}//stage Build ends
	}//stages ends
}//pipeline ends
