pipeline {
  agent any
   stages {
        stage('Build') {
          steps {
           bat 'docker build -t aya20/mern-server:latest ./server'
           bat 'docker build -t aya20/mern-client:latest ./client'
            }
         }

     stage('Test') {
            steps {
                script {
                    // Run tests for the server
                    bat 'docker run --rm aya20/mern-server:latest npm test'

                    // Run tests for the client
                    bat 'docker run --rm aya20/mern-client:latest npm test'
                }
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
