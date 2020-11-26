#!groovy

pipeline {
    agent any
    stages {
        stage('Smoke Test') {
            steps {
                dir('postman') {
                    nodejs('nodejs') {
                        sh "npm --version"
                    }
                }
            }
        }
    }
}
