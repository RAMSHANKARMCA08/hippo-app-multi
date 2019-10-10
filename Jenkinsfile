pipeline {
    agent any
    stages {
        stage('Client 1') {
		agent {  node { label
                client1 {
                reuseNode true
		}
			      }
            }
            	steps { sh 'echo "Client 1"' } 
        }
	 stage('Client 2') {
		agent {  node { label
                client2 {
                reuseNode true
                }
			      }
            }
            	steps { sh 'echo "Client 2"' } 
        }
    }
}

        
