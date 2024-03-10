pipeline {
    agent any
    stages {
        stage('Clone repository') {
          steps {
              checkout ([$class: 'GitSCM',
               branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/SHAMELESSKING1/PES2UG21CS182_Jenkins.git']]])
            }
         }
        stage('Build') {
            steps {
                build 'PES2UG21CS182-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage( 'Test') {
            steps {
                sh './output'
            }
        }
        stage( 'Deploy') {
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
