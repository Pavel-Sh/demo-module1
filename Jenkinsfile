pipeline {

    agent any

    stages {
        stage('publish artifact') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'aws', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh "export CODEARTIFACT_AUTH_TOKEN=`aws codeartifact get-authorization-token --domain test --domain-owner 748392735374 --region us-west-2 --query authorizationToken --output text`"
                    sh "chmod +x ./gradlew"
                    sh "./gradlew publish"
                }
            }
        }
    }
}