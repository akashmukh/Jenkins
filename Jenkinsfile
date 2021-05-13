pipeline {
    agent any

     stages {
        stage('Git Clone') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', credentialsId: '4af18a21-3317-4da0-85bc-1fbffb60821b', url: 'https://github.com/akashmukh/Jenkins.git'
            }
        }
        stage('Deployment'){
            steps {
                // move the new changed 
            sh 'rsync -av index.html akash@192.168.0.101:/var/www/html'
            }
        }
     }
}
