pipeline {
    agent any

    triggers {
        // Cron: Every day at 3:30 AM
        cron('30 3 * * *')
    }

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage('Clone Git Repository') {
            steps {
                git url: 'https://github.com/your-username/ci-cron-pipeline.git'
            }
        }

        stage('Run Scheduled Job via Ansible') {
            steps {
                sh '''
                    ansible-playbook -i inventory.ini cron_playbook.yml
                '''
            }
        }
    }
}
