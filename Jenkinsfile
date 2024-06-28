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
            deploy adapters: [tomcat9(credentialsId: 'a62c1e54-008f-4b15-acd0-b602dbfeb068', path: '', url: 'http://localhost:9999')], contextPath: 'weguidejune24', war: 'productweb/target/productweb.war'
         }
      }
   }
  
}
