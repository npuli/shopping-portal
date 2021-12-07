pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        echo 'this is the compile first job'
        sh 'npm install'
      }
    }

    stage('test') {
      steps {
        echo 'this is the test second job'
        sh 'npm test'
      }
    }

    stage('package') {
      steps {
        echo 'this is the package third job'
        sh 'npm run package'
      }
    }

    stage('archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}