pipeline{
    agent any
    stages
    {
        stage("Build")
        {
            steps{
                sh "mvn clean package"
            }
        }
    }
    stages
    {
        stage("Deploy")
        {
            steps{
                deploy adapters: [tomcat7(credentialsId: 'fd96e198-5399-4ced-b32a-d498c0ed643e', path: '',
                url: 'http://ec2-18-191-38-118.us-east-2.compute.amazonaws.com:9090/')],
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
