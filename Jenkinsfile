pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "built-in"
                }
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "Windows_Node"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On built-in') {
                    agent {
                        label "built-in"
                    }
                    steps {
			echo "Task1 on built-in"
		   }
                }
            }
        }
    }
}
