pipeline {
  agent any
  stages {
    stage('Clone repository') {
      steps {
        checkout([$class: 'GitSCM', 
                  branches: [[name: '*/main']], 
                  userRemoteConfigs: [[url: 'https://github.com/sruthiscodes/PES2UG22CS583_Jenkins']]
        ])
      }
    }
    stage('Build') {
      steps {
        sh 'g++ main/hello.cpp -o output'  // Compile the C++ file into an executable named output
      }
    }
    stage('Test') {
      steps {
        sh './output  // Run the compiled file
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying application...'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed'  // Print the failure message when the pipeline fails
    }
  }
}

