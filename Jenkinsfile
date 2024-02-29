pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Scan') {
      steps {
        withSonarQubeEnv(installationName: 'sq-poc') { 
          sh 'chmod +x mvnw'
          sh './mvnw clean verify sonar:sonar -Dsonar.projectKey=Jenkins-POC -Dsonar.host.url=<HOST_URL> -Dsonar.login=<ACCESS_KEY>'
        }
      }
    }
  }
}
