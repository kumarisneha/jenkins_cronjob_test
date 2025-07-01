pipeline {
  agent any

  triggers {
    cron('H/30 * * * *')  // Every 30 minutes
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/kumarisneha/jenkins_cronjob_test.git'
      }
    }

    stage('Run Ansible') {
      steps {
        dir('ansible') {
          sh 'ansible-playbook -i inventory get_kernel.yml'
        }
      }
    }
  }
}
