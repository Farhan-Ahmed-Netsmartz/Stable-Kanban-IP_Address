pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                input("Do you want to start production server?")
                echo 'Hello World'
                sshagent(['dev']) {
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.208.88.210 'ls'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.208.88.210 'git clone -b prod https://github.com/Farhan-Ahmed-Netsmartz/Stable-Kanban-IP_Address.git'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.208.88.210 'pwd' "
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.208.88.210 'ls'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.208.88.210 'cd Stable-Kanban-IP_Address && ls'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 172.208.88.210 'cd Stable-Kanban-IP_Address && docker-compose up -d'"
                }
            }
        }
    }
}
