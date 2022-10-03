pipeline {

    agent any

    stages {
        stage('publish artifact') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'aws', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh "chmod +x ./gradlew"
                    sh "./gradlew publish"
                }
            }
        }
    }
}