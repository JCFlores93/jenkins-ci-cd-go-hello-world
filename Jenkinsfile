pipeline {
    agent any
    environment {
        jenkins = "jenkins outside"
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableConcurrentBuilds()
    }
    stages {
        stage ("Hello") {
            environment {
                jenkins = "jenkins inside"
            }
            steps {
                echo "Hello"
                sh "env"
            }
        }
    }
    post{
        always{
            echo "====++++always++++===="
        }
        success{
            echo "====++++only when successful++++===="
        }
        failure{
            echo "====++++only when failed++++===="
        }
        changed {
           echo "====++++changed++++====" 
        }
        fixed {
            echo "====++++fixed++++===="
        }
        regression {
            echo "====++++regression++++===="
        }
        aborted {
            echo "====++++aborted++++===="
        }   
        failure {
            echo "====++++failure++++===="
        }
        success {
            echo "====++++success++++===="
        }
        unstable {
            echo "====++++unstable++++===="
        }
    }
}