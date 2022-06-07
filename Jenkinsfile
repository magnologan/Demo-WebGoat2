pipeline {
  agent any
  stages {
    stage ('DAST')
      steps {
        sh "docker run -t owasp/zap2docker-stable zap-baseline.py -t http://testphp.vulnweb.com" || true'
      }
  }
}
