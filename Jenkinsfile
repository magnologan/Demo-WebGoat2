pipeline {
  agent any
  stages {
    stage ('Check-Git-Secrets') {
      steps {
        sh 'rm trufflehog || true'
        sh 'docker run gesellix/trufflehog --json https://github.com/devopsadmin12/Demo-WebGoat.git > trufflehog'
        sh 'cat trufflehog'
      }
    }
    stage ('DAST') {
      steps {
        sh "docker run -t owasp/zap2docker-stable zap-baseline.py -t http://10.0.2.15:8081/WebGoat || true"
      }
   }
 }
}
