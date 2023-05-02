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
            deploy adapters: [tomcat8(credentialsId: '29210a83-2cda-43e4-9c50-fa984139bf64', path: '', url: 'http://localhost:9999')], contextPath: 'weguidePLMay123', onFailure: false, war: 'productweb/target/productweb.war'
         }
      }
   }
  
}
