pipeline{
    agent none
    stages {
        stage("Client 1"){
            agent { label 'client1' }
            steps{
		    steps { sh 'touch /home/centos/client1.txt' } 
            }
        }
    }
}

