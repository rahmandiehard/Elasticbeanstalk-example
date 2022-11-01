pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/rahmandiehard/MavenProject.git', branch: 'master'
             
            }
        }
        stage('Build') {
            steps {
             sh "mvn clean install"
             
            }
        }
        stage("S3 Upload"){
            steps{
                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding',accessKeyVariable: 'AWS_ACCESS_KEY_ID',credentialsId:'tfuser',secretKeyVariable:'AWS_SECRET_ACCESS_KEY']]) {
                sh "aws s3 cp /var/lib/jenkins/workspace/buildjob/target/MavenProject-0.0.1-SNAPSHOT.war s3://jenkinsbuildtoufiq"
               }    
            }
       }
    }
}
