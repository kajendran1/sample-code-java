pipeline
{
    agent any
    environment
    {
        PATH = "/usr/bin/:$PATH"
    }
    stages{
        stage("Git")
        {
            steps{
                git credentialsId: '48d5f80a-5851-4f96-9aee-f909eb748870', url: 'https://github.com/kajendran1/sample-code-java.git'
                echo 'suceesfully checkout'
            }
        }
        stage("Build")
        {
            steps{
                sh "mvn clean install"
                echo 'build suceesfull'
            }
        }
    }
}
