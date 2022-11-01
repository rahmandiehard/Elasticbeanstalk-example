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
        stage("Upload"){
        withAWS(region:"us-east-1", credentials:"${aws_credential}"){
                    s3Upload(file:"/var/lib/jenkins/workspace/buildjob/target/Elasticbeanstalk-example-0.0.1-SNAPSHOT.war", bucket:"jenkinsbuildtoufiq", path:"/var/lib/jenkins/workspace/buildjob/target/Elasticbeanstalk-example-0.0.1-SNAPSHOT.war/")
                } 
       }
        
    }
}
