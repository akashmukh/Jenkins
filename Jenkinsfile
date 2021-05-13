def remote = [:]
remote.name = 'test'
remote.host = '18.209.87.84'
remote.port = 22
remote.allowAnyHosts = true

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
             sh 'ls'
             //sh 'scp index.html ubuntu@18.209.87.84:/var/www/html'
             withCredentials([usernamePassword(credentialsId: 'ubuntu-ec2', passwordVariable: 'pass', usernameVariable: 'user')]) {
             sshPut remote: remote, from: "index.html", into: "/var/www/html"
             sshCommand remote: remote, command: "ls /var/www/html"
             }
           }
        }
    }
}
