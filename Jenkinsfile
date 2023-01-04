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
          sh './mvnw clean verify sonar:sonar -Dsonar.projectKey=Jenkins-POC -Dsonar.host.url=http://51.116.138.213:9000 -Dsonar.login=sqp_4222a9a294d090c008a240d7a0377ea3f3c1967e'
        }
      }
    }
  }
}
