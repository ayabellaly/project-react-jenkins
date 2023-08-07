pipeline {
    agent any

    stages {
        stage('Stage 1') {
            steps {
                // echo 'hello'
            }
        }

        stage('Stage 2') {
            steps {
                // echo 'step 2'
            }
        }
    }

    post {
        success {
            // echo 'hala hala'
        }

        failure {
            // echo 'lah lah'
        }
    }
}
