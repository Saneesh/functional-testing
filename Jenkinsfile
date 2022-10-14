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
         post {
          success publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'TestReport', reportFiles: 'TestReport.html', reportName: 'HTML Report', reportTitles: 'Functional test report', useWrapperFileDirectly: true])
         }
    }
  }
}
