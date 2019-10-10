pipeline{
    agent none
    stages {
        stage("Client 1"){
            agent { label 'client1' }
            steps{
		    sh 'echo $PWD' 
            }
        }
    }
}

