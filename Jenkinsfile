pipeline{
  agent any
  stages {
          stage('Clone repository'){
            steps {
              checkout([$class: 'GitSCM',
              branches: [[name: '*/main']],
              userRemoteConfigs: [[url: '']]])
            }
          }
    stage('Build'){
        steps {
          build 'PES2UG21CS514-1'
          sh 'g++ HelloWorld.cpp -o output'
        }
    }
    stage('Test'){
      steps{
        sh './output'
      }
    }
    stage('Deploy') {
        steps {
            echo 'deploy'
        }
    }
}
post{
  failure{
    error 'Pipeline failed'
  }
}
}
