#!groovy

pipeline {
    agent any
    stages {
        stage('Smoke Test') {
            steps {
                bat "newman run Pet_Store.postman_collection.json -e Pet_Store_Live.postman_environment.json -r htmlextra --reporter-htmlextra-export ./${currentBuild.number}"
            }
            post {
                success {
                  // publish html
                  publishHTML target: [
                      allowMissing: false,
                      alwaysLinkToLastBuild: false,
                      keepAll: true,
                      reportDir: '${currentBuild.number}',
                      reportFiles: '*.html',
                      reportName: 'Test Report'
                    ]
                }
            }
        }
    }
}
