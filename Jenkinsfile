pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/veturitrivek/triveksunny.git'
      }
    }
    stage('Build & Deploy') {
      steps {
        sh '''
          cd /root/project/triveksunny
          docker-compose down
          docker-compose build
          docker-compose up -d
        '''
      }
    }
  }
}
