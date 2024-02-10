pipeline {
     agent {label 'jenkins-agent'}
     tools {
          jdk 'Java17'
          maven 'Maven3'
      }
      stages{
          stage ("cleanup Workspace"){
                  steps {
                  cleanWs()
                  }
          }

          stage("checkout from SCM"){
                  steps {
                  git branch: 'main', credentialsId: 'github', url: 'https://github.com/KiVi06/app.git'
                  }
          }

          stage("Build Application"){
               steps {
                      sh "mvn clean package"
               }
           }

           stage("Test Application"){
               steps {
                      sh "mvn test"
               }
           }
      }
}
