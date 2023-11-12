pipeline {
  agent any
  stages {
    stage('Fluffy Build') {
      steps {
        echo 'Placeholder'
        sh 'echo "Edited Placeholder"'
        sh './jenkins/build.sh'
      }
    }

    stage('Fluffy Test') {
      steps {
        sh 'sleep 5'
        sh 'echo "Success!"'
        sh './jenkins/test-all.sh'
      }
    }

    stage('Fluffy Deploy') {
      steps {
        echo 'Placeholder'
        sh './jenkins/deploy.sh staging'
      }
    }

  }
}