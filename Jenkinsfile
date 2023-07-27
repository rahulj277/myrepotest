pipeline {
    /* specify nodes for executing */
    agent any 

    environment {
        GITHUB_API_URL='https://api.github.com/repos/rahulj277/myrepotest'
    }

    stages {
        stage('Do the deployment') {
            steps {
                echo ">> Run deploy applications "
                sh "ls -l"
                sh "cat testing.txt"
            }
        }
    }
 
    /* Cleanup workspace */
    post {
        success {
            withCredentials([usernamePassword(credentialsId: 'githubtoken', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
            sh 'curl -X POST --user $USERNAME:$PASSWORD --data  "{\\"state\\": \\"success\\"}" --url $GITHUB_API_URL/statuses/$GIT_COMMIT'
            }
        }
        failure {
            withCredentials([usernamePassword(credentialsId: 'githubtoken', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
            sh 'curl -X POST --user $USERNAME:$PASSWORD --data  "{\\"state\\": \\"failure\\"}" --url $GITHUB_API_URL/statuses/$GIT_COMMIT'
            }
        }
       always {
           deleteDir()
        }
    }
}