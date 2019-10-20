pipeline {
    agent any
    stages {
        stage('Git') {
            steps { git 'https://github.com/RAMSHANKARMCA08/hippo-app-multi.git' }
        }
	stage('Build') {
		steps {  
			dir("/var/lib/docker/volumes/jenkins_home/_data/workspace/hippo-app") {
			withDockerContainer(image:'maven:3.5.0-jdk-8-alpine')
				{       sh "$pwd"
					sh "sudo mvn clean install"}
       			// archiveArtifacts '**/target/spring-boot-web-jsp-1.0.war'			
			}}
	}
}
}
