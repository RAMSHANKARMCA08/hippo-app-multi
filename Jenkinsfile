pipeline {
    agent any
    stages {
        stage('Client 1') {
		agent {  
                client1 {
                reuseNode true
                }
            }
            	steps { sh 'echo "Client 1"' } 
        }
	 stage('Client 2') {
		agent {  
                client2 {
                reuseNode true
                }
            }
            	steps { sh 'echo "Client 2"' } 
        }
    }
}

        
