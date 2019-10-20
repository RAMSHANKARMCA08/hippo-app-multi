pipeline {
    agent any
    stages {
        stage('Git') {
            steps { git 'https://github.com/RAMSHANKARMCA08/hippo-app.git' }
        }
	stage('Build') {
		steps {  
			withDockerContainer("maven:3.5.0-jdk-8-alpine") { sh "mvn clean install"}
       			 archiveArtifacts '**/target/spring-boot-web-jsp-1.0.war'			
    }
	}
}
}
