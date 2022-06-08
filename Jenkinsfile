pipeline {
  agent any
  stages {
      stage ('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            ''' 
      }
    }
      stage ('Source Composition Analysis') {
      steps {
         sh 'rm owasp* || true'
         sh 'wget "https://raw.githubusercontent.com/devopsadmin12/Demo-WebGoat/master/owaspdependencycheck.sh" '
         sh 'chmod +x owaspdependencycheck.sh'
         sh 'bash owaspdependencycheck.sh'
         sh '/{var/lib/jenkins/dependency-check/bin/dependency-check.sh --scan `pwd` --format JSON --out /{var/lib/jenkins}/reports/dependency-check-report --prettyPrint''
      }
    }
 }
}
