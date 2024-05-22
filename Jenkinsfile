pipeline {
    agent any
    
    triggers {
        githubPush()
    }
    
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sshagent(['dev']) {
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.212.98.164 'ls'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.212.98.164 'git clone -b dev https://github.com/Farhan-Ahmed-Netsmartz/Stable-Kanban-IP_Address.git'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.212.98.164 'pwd' "
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.212.98.164 'ls'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.212.98.164 'cd Stable-Kanban-IP_Address && ls'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.212.98.164 'cd Stable-Kanban-IP_Address && docker-compose up -d'"
                }
            }
        }
    }
}
