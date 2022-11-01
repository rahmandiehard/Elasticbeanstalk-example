pipeline {
    agent any
    stages {
        stage('clone') {
            steps {
                git url: 'https://github.com/rahmandiehard/MavenProject.git', branch: 'master'
             
            }
        }
        stage('BuildProject') {
            steps {
             sh "mvn clean install"
             
            }
        }
    }
}
