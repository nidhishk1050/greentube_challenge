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
		sh "sudo docker push nidhishd/greentube_feature_nd_working_web:latest"
		
	  
            }
        }
	 
    }
}
