    def remote = [:]
    remote.name = 'akash'
    remote.host = '192.168.0.101'
    remote.user = 'akash'
    remote.password = 'akash'
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
        //stage('Deployment'){
            //steps {
                // move the new changed 
            //sh 'scp index.html akash@192.168.0.101:/var/www/html'
            //}
        //}
       stages('Remote SSH') {
           steps {
        sshPut remote: remote, from: 'index.html', into: '/var/www/html'
         }
       }
    }
}
