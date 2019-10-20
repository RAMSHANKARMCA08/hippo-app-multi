pipeline {
    agent any
    stages {
        stage('Git') {
            steps { git 'https://github.com/RAMSHANKARMCA08/hippo-app.git' }
        }
	stage('Build') {
		steps {  
			withDockerContainer(args: '-it --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven', image: 'maven:3.3-jdk-8')
				{ sh "mvn clean install"}	
				}				
    }
	}
}
