//def remote = [:]
//remote.name = 'test'
//remote.host = '18.209.87.84'
//remote.port = 22
//remote.allowAnyHosts = true


pipeline {
    agent any

     stages {
        stage('Git Clone') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/akashmukh/Jenkins.git'
            }
        }
     stage('Deployment'){
        steps {
            script {
             // move the new changed 
             //sh '''
               // echo "echo hello world" >> test.sh
                //cat test.sh
             //'''
             sh 'mv index.html /var/www/html'
             //withCredentials([usernamePassword(credentialsId: 'ubuntu-ec2', passwordVariable: 'pass', usernameVariable: 'user')]) {
             //remote.user = user
             /remote.password = pass
             //sshPut remote: remote, from: "index.html", into: "/var/www/html"
             //sshPut remote: remote, from: "test.sh", into: "/tmp"
             //sshCommand remote: remote, command: "ls /var/www/html && chmod +x /tmp/test.sh"
             //sshScript remote: remote, script: 'test.sh'
             }
            }
            }
        }
    }
}
