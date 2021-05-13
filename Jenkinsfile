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
             sh 'whoami'
             sh 'pwd && ls /var/lib/jenkins'
             sh 'scp -i /var/lib/jenkins/training.pem index.html ubuntu@18.209.87.84:/var/www/html'
            }
        }
    }
}
