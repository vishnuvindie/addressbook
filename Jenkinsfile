pipeline {
  agent any
  stages {
    stage('Branches') {
      options {
        timeout(unit: 'SECONDS', time: 2)
      }
      parallel {
        stage('Development Branch') {
          steps { echo 'Building Development Branch' }
        }
        stage('Production Branch') {
          steps {
            echo 'Building Production Branch'
            echo 'Signing files'
          }
        }
      }
    }
    post {
      changed { echo 'Found a change' }
    }
  }
}
