pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        bat 'docker build -t my-flask-app .'
      //   bat 'docker tag my_flask_app %DOCKER_BFLASK_IMAGE%'
      }
    }
    stage('Test') {
      steps {
        bat 'docker run my-flask-app python -m pytest app/tests/'
      }
    }
    // stage('Deploy') {
    //   steps {
    //     withCredentials([usernamePassword(credentialsId: "${DOCKER_REGISTRY_CREDS}", passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
    //       bat "echo %DOCKER_PASSWORD% | docker login -u %DOCKER_USERNAME% --password-stdin docker.io"
    //       bat 'docker push %DOCKER_BFLASK_IMAGE%'
    //     }
    //   }
  //   }
  // }
  // post {
  //   always {
  //     bat 'docker logout'
  //   }
  // }
}
}
