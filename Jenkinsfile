pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/Liam301020/8.2CDevSecOps.git'
      }
    }
    stage('Install Dependencies') {
      steps { sh 'npm install || true' }
    }
    stage('Run Tests') {
      steps { sh 'npm test || true' }
    }
    stage('Generate Coverage Report') {
      steps { sh 'npm run coverage || true' }
    }
    stage('NPM Audit (Security Scan)') {
      steps {
        sh 'npm audit || true'
        sh 'npm audit --json > audit.json || true'
      }
    }
  }
}
