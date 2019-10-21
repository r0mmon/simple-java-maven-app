pipeline {
  agent  {
    label "jenkins-maven"
  }
  stages {
    stage('Build') {
      steps {
        container('maven') {
          sh 'mvn -B -DskeipTests clean package'
        }
      }
    }
  }
}