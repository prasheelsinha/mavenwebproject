pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'df30cb7c-8cbb-4b68-aa29-f81efff6a2e4', 
                path: '', 
                url: 'http://ec2-13-232-15-62.ap-south-1.compute.amazonaws.com:8080')],
                contextPath: 'javawebapppipeline', onFailure: false, war: '**/web-project.war'
            }
        }
    }
}
