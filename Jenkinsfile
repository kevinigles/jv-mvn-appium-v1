pipeline {
    agent any
    parameters {
        string(name: 'Test', defaultValue: 'google', description: 'Seleccionar el test a ejecutar : \n - google \n - google_pop')
    }
    stages {
        stage('Build') {
            steps {
                echo '***********************'
                echo '** Building Project ** '
                echo '***********************'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
              echo '********************'
              echo '** Testing Suite ** '
              echo '********************'
              sh 'npm run ${Test}'
            }
        }
    }
    post {
        always {
           junit '*.xml'
        }
    }
}
