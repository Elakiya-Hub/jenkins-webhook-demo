pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code is available from GitHub.'
            }
        }

        stage('Run Script') {
            steps {
                sh '''
                chmod +x demo.sh
                ./demo.sh
                '''
            }
        }

    }
}
