pipeline {
    agent {
        docker {
            image 'cytopia/ansible'
        }
    }
    stages {
        stage('Ansible Playbook') {
            steps {
                credentialsId: 'vm-credentials'
                script {
                    sh 'ansible-playbook playbook.yml -i Hostfile'
                }
             }
         }
        stage('build') {
            steps {
                sh 'echo building ...'
                sh "echo gansefusse test ... "
                sh "which python || true"
                sh "which python3 || true"
                sh "which ansible || true"
                sh "ansible --version"
            }
        }
        stage('test') {
            steps {
                sh 'echo testing ...'
            }
        }
        stage('deploy') {
            steps {
                sh 'echo deploying ...'
            }
        }
    }
}
