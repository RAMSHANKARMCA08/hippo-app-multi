pipeline{
    agent none
    stages {
        stage("Client 1"){
            agent { label 'client1' }
            steps{
		    steps { sh 'echo "Client 1"' } 
            }
        }
	    stage("Client 2"){
            agent { label 'client2' }
            steps{
		    steps { sh 'echo "Client 2"' } 
            }
        }
    }
}

