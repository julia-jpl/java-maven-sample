pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn compile'
                echo 'Build compiled'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
                echo 'Build tested'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
                echo 'Build packaged'
            }
            post {
  always {
    // One or more steps need to be included within each condition's block.
        junit 'target/surefire-reports/*.xml'
  }
  success {
      archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
  }
  
}
        
        }
    }
}
