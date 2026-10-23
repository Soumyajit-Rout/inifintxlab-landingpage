pipeline {
  agent any
  
  stages {
    stage('compile')  { 
      steps { sh 'mvn compile' } 
    }
    stage('test')     {
      steps { sh 'mvn test' } 
    }
    stage('package')  {
      steps {
        sh 'mvn clean package'
        sh 'mv target/*.war target/myweb.war'
      }
    }
    stage('to Tomcat') {
      steps {
        sshagent(['tomcat-ssh-key']) {
          sh 'scp -o StrictHostKeyChecking=no target/myweb.war root@64.227.164.125:/root/tomcat8/webapps'
        }
      }
    }
  }
}
