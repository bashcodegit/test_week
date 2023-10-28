node {
  stage('SCM') {
    checkout scm
  }
  stage('Test') {
    echo 'Application Testing'
  }
  stage('Test'){
      sh 'python3 manage.py test'
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
