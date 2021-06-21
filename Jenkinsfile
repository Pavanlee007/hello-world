pipeline {
  agent any
      stages {
       stage('scm checkout'){
         steps {
         git url: 'https://github.com/Pavanlee007/hello-world.git'
       }
     }
       stage('build'){
         steps {
         sh 'mvn clean install package' 
       }
     }
       stage('Deploy'){
         steps {
         deploy adapters: [tomcat10(credentialsId: 'deployer_deployer', url: 'http://ec2-54-145-165-198.compute-1.amazonaws.com:8090/')], contextPath: 'Null', war: '**/*.war'
         }
       }  
     }
}
