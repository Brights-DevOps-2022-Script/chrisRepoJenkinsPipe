pipeline {
    agent {
        docker {
            image 'cytopia/ansible'
        }
    }
    environment {
        ANSIBLE_KEY = credentials('ansCred')
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }
    stages {
        stage('Ansible Playbook') {            
            steps {
                script {
                    sh 'apk update'
                    sh 'apk add --update --no-cache openssh sshpass'
                    sh 'ansible-playbook playbook.yml -i Hostfile -e ansible_ssh_pass=$ANSIBLE_KEY_PSW -e ansible_user=$ANSIBLE_KEY_USR'
                }
             }
         }
        stage('test') {
            steps {
                sh 'echo building ...'
                sh "ansible --version"
            }

            
        }
    }
}
