pipeline {
  agent any
  stages {
    stage('Fluffy Build') {
      steps {
        echo 'Placeholder'
        sh 'echo "Edited Placeholder"'
        sh './jenkins/build.sh'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

    stage('Backend') {
      parallel {
        stage('Backend') {
          steps {
            sh './jenkins/test-backend.sh'
            junit 'target/surefire-reports/**/TEST*.xml'
          }
        }

        stage('Frontend') {
          steps {
            sh './jenkins/test-frontend.sh'
            junit 'target/test-results/**/TEST*.xml'
          }
        }

        stage('Performance') {
          steps {
            sh './jenkins/test-performance.sh'
          }
        }

        stage('Static') {
          steps {
            sh '''./jenkins/test-static.s
'''
          }
        }

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