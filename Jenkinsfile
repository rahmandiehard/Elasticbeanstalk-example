pipeline {
    agent any
    stages {
        stage('clone') {
            steps {
                // Get  code from a GitHub repository
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
