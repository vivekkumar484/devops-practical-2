pipeline {
    agent any
	

 stages {
      stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/srikanta1219/devops-practical-2.git'
             
          }
        }
       

  stage('Docker Build and Tag') {
           steps {
              
                sh 'docker build -t devopsclass:latest .' 
                sh 'docker tag devopsclass srikanta1219/devopsclass:$BUILD_NUMBER'
               
          }
        }
  stage('Publish image to Docker Hub') {
            steps {
        withDockerRegistry([ credentialsId: "dockerHub", url: "" ]) {
           sh  'docker push srikanta/samplewebapp:$BUILD_NUMBER' 
		}
                  
          }
        }
		
    }
}
