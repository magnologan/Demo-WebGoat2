pipeline {
  agent any
  stages {
    stage ('Source Composition Analysis') {
      stage ('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            ''' 
      }
    }
      steps {
         sh 'rm owasp* || true'
         sh 'wget "https://raw.githubusercontent.com/devopsadmin12/Demo-WebGoat/master/owaspdependencycheck.sh" '
         sh 'chmod +x owaspdependencycheck.sh'
         sh 'bash owaspdependencycheck.sh'
         sh 'cat /var/lib/jenkins/OWASP-Dependency-Check/reports/dependency-check-report.xml'
      }
    }
 }
}
