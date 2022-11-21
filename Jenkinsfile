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
          sh './mvnw clean verify sonar:sonar -Dsonar.projectKey=teo-common -Dsonar.host.url=http://51.116.138.213:9000 -Dsonar.login=squ_c94f0ef7f370560ade2ae5ff335281495ddde214'
        }
      }
    }
  }
}
