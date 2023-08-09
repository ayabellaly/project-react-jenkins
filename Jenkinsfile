pipeline {
  agent any
   stages {
        stage('Build') {
          steps {
           bat 'docker build -t aya20/mern-server:latest ./server'
           bat 'docker build -t aya20/mern-client:latest ./client'
            }
         }
        stage('Push') {
         steps{
               withDockerRegistry([credentialsId: "aya-dockerhub", url: ""])
               {
                  bat 'docker push aya20/mern-server:latest'
                  bat 'docker push aya20/mern-client:latest'
               }
         } 
      }
    }
   }
