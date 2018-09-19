pipeline {
  agent any
  stages {
    stage('Compilacion') {
      steps {
        sh 'docker build -t mi_proyecto .'
      }
    }
    stage('Despliegue') {
      steps {
        sh 'docker run --rm -p 8585:8585 -d --name=HelloWorldSpringBootApp mi_proyecto'
      }
    }
    stage('Detener') {
      steps {
        input 'Desea detener?'
        sh 'docker stop HelloWorldSpringBootApp'
      }
    }
  }
}