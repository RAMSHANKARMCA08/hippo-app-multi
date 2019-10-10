pipeline{
    agent none
    stages {
        stage("Client 1"){
            agent { label 'client1' }
            steps{
		    steps { sh 'touch client1' } 
            }
        }
	    stage("Client 2"){
            agent { label 'client2' }
            steps{
		    steps { sh 'touch client2' } 
            }
        }
    }
}

