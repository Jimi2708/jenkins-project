pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
      jdk 'java17'
      maven 'Maven3'
    }
    stages{
      stage ("Cleanup Workspace"){
              steps {
              cleanWs()
              }
      }

      stage ("Checkout feom SCM"){
                steps {
                 git branch: 'main', credentialsId: 'github', url: 'https://github.com/Jimi2708/jenkins-project.git'
                }
      }

      stage ("Build Application"){
        steps {
          sh "mvn clean package"
        }
        
     }

      stage ("Test Application"){
        steps {
              sh "mvn test"
        }

      }
      
    }
}
  
