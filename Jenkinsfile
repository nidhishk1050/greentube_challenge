pipeline { 
    agent any 
    stages {
        stage('Checkout') { 
            steps { 
            
		checkout(scm)

            }
        }
        stage('Build'){
            steps {
      
     		sh "sudo docker-compose up -d "
		sh "sudo docker images"
		sh "sudo docker ps -a"
		
	  
            }
        }
        stage('Unit Test') {
            steps {
			sh "docker-compose -p tests run -p 3000 --rm web npm run test --forceExit"
		        junit 'test-results.xml'
            }
        }
	 
    }
}
