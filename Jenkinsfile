pipeline {
  agent any
  tools {
    maven 'Maven' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8(credentialsId: '32c424a6-647a-43aa-81b7-2c303fc43c6a', path: '', url: 'http://ec2-3-86-205-186.compute-1.amazonaws.com:8080/')], contextPath: null, war: '**/*.war'
        }
      }
    }
  }
}
