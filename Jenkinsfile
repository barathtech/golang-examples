pipeline {
    agent any
    tools {
        go 'go1.18'
    }
    environment {
       GO114MODULE = 'on'
       CGO_ENABLED = 0 
       GOPATH = "${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}"
    }
     stages { 
       stage('Build') {
            steps {
               git url: https://github.com/barathtech/helloworld-web-go.git    
            }
        }

        stage('Test') {
            steps {
                sh 'curl -sfL https://install.goreleaser.com/github.com/golangci/golangci-lint.sh | bash -s -- -b $GOPATH/bin v1.12.5'
                sh 'go version'
                sh ' cd /var/lib/jenkins/workspace/demo/beginner '
                sh  "go run main.go"
             }
          }
       } 
    } 
