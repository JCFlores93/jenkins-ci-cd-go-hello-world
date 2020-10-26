pipeline {
    agent any
    environment {
        jenkins = "jenkins outside"
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableConcurrentBuilds()
    }
    parameters {
        string(name: "Person", defaultValue: "Jenkins", description: "Set your name")
    }
    triggers {
        // cron
        // pollSCM
        // upstream
        cron { "H/15 * * * *"}
    }
    // tools {
    //     // jdk
    //     // maven
    //     // gradle
    //     // nodejs
    // }
    stages {
        stage ("Hello") {
            input {
                message "Desplegar a prod"
                ok "SI, desplegar"
                submitter "jlrm, clark"
            }
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
        unstable {
            echo "====++++unstable++++===="
        }
    }
}