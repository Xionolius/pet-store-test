#!groovy

pipeline {
    agent any
    stages {
        stage('Smoke Test') {
            steps {
                bat "newman run Pet_Store.postman_collection.json -e Pet_Store_Live.postman_environment.json -r htmlextra"
            }
        }
    }
}
