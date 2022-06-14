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
            deploy adapters: [tomcat8(credentialsId: 'tomcat', path: '', url: 'http://localhost:9999')], contextPath: 'weguidechaiPT', war: 'productweb\\target\\productweb.war'
         }
      }
   }
  
}
