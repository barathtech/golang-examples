pipeline {
    agent any
    tools {
      go 'go1.13.8'
    }
     stages { 
      stage('Build') {
        steps {
               git url: https://github.com/barathtech/helloworld-web-go.git    
            }
        }

      stage('Test') {
        steps {
             sh''' go version ''
             }
          }
       } 
    } 
