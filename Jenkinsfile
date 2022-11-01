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
        try{
               withCredentials([<object of type com.cloudbees.jenkins.plugins.awscredentials.AmazonWebServicesCredentialsBinding>]) {
                sh "aws s3 ls"
                sh "aws s3 cp /var/lib/jenkins/workspace/buildjob/target/Elasticbeanstalk-example-0.0.1-SNAPSHOT.war s3://jenkinsbuildtoufiq"
              }   
            catch(err){
                sh "echo error"
            }
       }
        
    }
}
