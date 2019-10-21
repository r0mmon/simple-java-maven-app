pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        container('maven:3-apline') {
          sh 'mvn -B -DskeipTests clean package'
        }
      }
    }
  }
}