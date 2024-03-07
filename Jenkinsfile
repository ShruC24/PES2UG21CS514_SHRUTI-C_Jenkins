pipeline{
  agent any
  stages {
          stage('Clone repository'){
            steps {
              checkout([$class: 'GitSCM',
              branches: [[name: '*/main']],
              userRemoteConfigs: [[url: 'https://github.com/ShruC24/PES2UG21CS514_SHRUTI-C_Jenkins.git']]])
            }
          }
    stage('Build'){
        steps {
          build 'PES2UG21CS514-1'
          sh 'g++ sample.cpp -o output'
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
