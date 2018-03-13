pipeline {
  agent {
    node {
      label 'docker'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        echo 'I\'m building something cool'
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sleep 1
          }
        }
        stage('Win Test') {
          steps {
            echo 'command.com'
          }
        }
        stage('RHEL7.2 test') {
          steps {
            echo 'RHEL'
          }
        }
        stage('CentOS') {
          steps {
            sleep 2
          }
        }
      }
    }
    stage('Int Test') {
      steps {
        echo 'all the things'
        echo 'Notify QA Team'
        input(ok: 'Deploy', message: 'Deploy to QA', submitter: 'elong')
      }
    }
    stage('QA DEPLOY') {
      steps {
        echo 'deployed'
      }
    }
    stage('Prod') {
      steps {
        echo 'Prod'
      }
    }
  }
  environment {
    foo = 'bang'
    this = 'that'
  }
}