pipeline{
    agent none
    stages {
        stage("Step 1"){
            agent { label 'client1' }
            steps{
		    sh 'echo $PWD' 
            }
        }
        stage("Step 2"){
            agent { label 'java' }
            steps{
		    sh 'sudo java.txt' 
            }
	 
    }
}
}

