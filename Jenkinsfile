pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build Completed'
        retry(count: 3) {
          echo 'this try build three times to excute this step'
        }

      }
    }

    stage('Test Stages') {
      parallel {
        stage('Test1') {
          steps {
            echo 'Running Test 1'
          }
        }

        stage('Test2') {
          steps {
            echo 'Running Test 2'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Are you sure to deploy ?', ok: 'Yes, I am sure')
        echo 'Deploy Completed'
      }
    }

    stage('Notify for new Build') {
      steps {
        echo 'New Build Completed successfully'
      }
    }

  }
}