pipeline {
	
	environment {
    registry = "oussama24/pipeline_cicd"
    registryCredential = 'dockerhub'
  }
    agent any

    stages {
        stage('build') {
            steps {
        sh 'npm install'
	sh 'npm run build'
            }
        }
    }
	stage('Building image') {
      steps{
        script {
          docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
}
