pipeline {
  agent any
  stages {
    stage ('Source Composition Analysis') {
      steps {
         sh 'rm owasp* || true'
         sh 'wget "https://raw.githubusercontent.com/devopsadmin12/Demo-WebGoat/master/owaspdependencycheck.sh" '
         sh 'chmod +x owaspdependencycheck.sh'
         sh 'bash owaspdependencycheck.sh'
      }
    }
 }
}
