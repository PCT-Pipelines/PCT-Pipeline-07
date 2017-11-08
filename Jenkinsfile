pipeline {
  agent {
    node {
      label 'maven'
    }
    
  }
  stages {
    stage('License - checks') {
      steps {
        git(url: 'http://git.app.eng.bos.redhat.com/git/jboss-prod-core/gates.git/', branch: 'master')
        load 'gates/licenses/RunGate.groovy'
      }
    }
    stage('CVEs - checks') {
      steps {
        load 'gates/cves/RunGate.groovy'
      }
    }
    stage('Crypto - checks') {
      steps {
        load 'gates/crypto/RunGate.groovy'
      }
    }
    stage('Source code - checks') {
      steps {
        load 'gates/sourcecodelocation/RunGate.groovy'
      }
    }
  }
}