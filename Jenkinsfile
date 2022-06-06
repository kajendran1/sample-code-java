pipeline{
  agent any
  stages{
    stage('checkout'){
          steps{
             url: 'https://github.com/kajendran1/sample-code-java.git'
          }
       }
 
    stage('Build'){
          steps{
            sh 'mvn clean install'
          }
       }
   stage('Docker Image') {
            steps {
                script {
                  sh 'docker build -t kaj'
                }
            }
     }
    stage('deploy docker image'){
      steps {
        script {
          withCredentials([usernameColonPassword(credentialsId: 'kajendran1', variable: 'dockerpawd')]) {
    sh 'docker login -u kajendran1 -p ${dockerpawd}'
}
          sh 'docker push kajendran1/my-app-1.0 .'
        }
      }
    }
}
}
