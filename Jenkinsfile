pipeline{
    agent none
    stages {
        stage("Step 1"){
            agent { label 'client1' }
            steps{
		    sh 'echo $PWD' 
            }
        }
    stages {
        stage("Step 2"){
            agent { label 'java' }
            steps{
		    sh 'sudo java.txt' 
            }
	   agent { label 'maven' }
            steps{
		    sh 'sudo maven.txt' 
            }
	  agent { label 'maven2' }
            steps{
		    sh 'sudo maven2.txt' 
            }
	agent { label 'master' }
            steps{
		    sh 'sudo master.txt' 
            }
        }
    }
}
}

