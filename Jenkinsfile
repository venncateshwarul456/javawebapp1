pipeline {
   agent any

   stages {
      stage('clean') {
         steps {
            bat 'mvn clean'
         }
      }
      stage('package') {
         steps {
            bat 'mvn install'
         }
      }
      stage('deploy') {
         steps {
            deploy adapters: [tomcat9(credentialsId: '9eb02886-64e9-4aa9-9fd3-40b38bed226f', path: '', url: 'http://localhost:9999')], contextPath: 'PLTOct2425', war: 'productweb/target/productweb.war'
         }
      }
   }
  
}
