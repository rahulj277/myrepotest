pipeline {
    /* specify nodes for executing */
    agent any
 
    stages {
        stage('Do the deployment') {
            steps {
                echo ">> Run deploy applications "
                sh "cat testing"
            }
        }
    }
 
    /* Cleanup workspace */
    post {
       always {
           deleteDir()
       }
   }
}