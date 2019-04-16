pipeline {
  agent any
  stages {
    stage('SCM') {
        git 'https://github.com/NetworkBytes/flask-restplus-sample.git'
      }
      stage('SonarQube analysis') {
        def scannerHome = tool 'SonarQube';
        withSonarQubeEnv('SonarQube') {
          sh "${scannerHome}/bin/sonar-scanner -Dproject.settings=./sonar-project.properties"
        }
      }
      stage('Build image') {
        steps {
          echo 'Starting to build docker image'

          script {
              //def customImage = docker.build("simpleflash:${env.BUILD_ID}")
              //#customImage.push()
          }
        }
      }
  }
}
