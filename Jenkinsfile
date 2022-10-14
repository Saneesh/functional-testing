pipeline {
     agent any
  tools {
    maven "MVN3"
  }
  
  stages {
    stage('pullscm') {
      steps {
        git branch: 'main', credentialsId: 'github-credential', url: 'git@github.com:Saneesh/jenkins_test.git'
      }
    }
    stage('execute test') {
      steps {
        sh "mvn clean test"
      }
    }
  }
}
