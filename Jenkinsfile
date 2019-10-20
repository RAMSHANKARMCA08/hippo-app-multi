pipeline {
    agent any
    
	stages {
        stage('Git') {
            steps { git 'https://github.com/RAMSHANKARMCA08/hippo-app-multi.git' }
        }// stage git ends
	
	
	stage('Build') {
		steps {  
			dir("/var/lib/docker/volumes/jenkins_home/_data/workspace/hippo-app/") {
			withDockerContainer(args: '-it --rm --name my-maven-project -v /var/lib/docker/volumes/jenkins_home/_data/workspace/hippo-app -w /var/lib/docker/volumes/jenkins_home/_data/workspace/hippo-app mvn clean install', image: 'maven:3.5.0-jdk-8-alpine') {
   				 echo "Inside Block"
			}
       			// archiveArtifacts '**/target/spring-boot-web-jsp-1.0.war'			
			}			
			}
			
		}//stage Build ends
	}//stages ends
}//pipeline ends
