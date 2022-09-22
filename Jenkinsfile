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
            deploy adapters: [tomcat8(credentialsId: 'ced81644-d368-474a-9b1b-dc10c173264f', path: '', url: 'http://localhost:9999')], contextPath: 'TestPL', war: 'productweb/target/productweb.war'
         }
      }
   }
  
}
