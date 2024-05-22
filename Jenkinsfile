pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                input("Do you want to start UAT:")
                sshagent(['dev']) {
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 20.102.109.175 'ls'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 20.102.109.175 'git clone -b uat https://github.com/Farhan-Ahmed-Netsmartz/Stable-Kanban-IP_Address.git'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 20.102.109.175 'pwd' "
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 20.102.109.175 'ls'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 20.102.109.175 'cd Stable-Kanban-IP_Address && ls'"
                sh "ssh -o StrictHostKeyChecking=no -l azureuser 20.102.109.175 'cd Stable-Kanban-IP_Address && docker-compose up -d'"
                }
            }
        }
    }
}
