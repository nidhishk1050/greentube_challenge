pipeline { 
    agent any 
    stages {
        stage('Checkout') { 
            steps { 
            
			checkout scm

            }
        }
        stage('Build'){
            steps {
      
	        sh "docker-compose build"   
     		sh "docker-compose up -d "
		
	  
            }
        }
        stage('Test') {
            steps {
			sh "docker-compose -p tests run -p 3000 --rm web npm run watch-tests"
            }
        }
    }
}
