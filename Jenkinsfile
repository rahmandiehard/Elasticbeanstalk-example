pipeline {
    agent any
    tools {
        maven "maven-3.8.1"
           }
    stages {
        stage('clone') {
            steps {
                // Get some code from a GitHub repository
                git url: 'https://github.com/rahmandiehard/Elasticbeanstalk-example.git', branch: 'master'
             
            }
        }
        stage('Build') {
            steps {
             sh "mvn clean install"
             
            }
        }
    }
}
