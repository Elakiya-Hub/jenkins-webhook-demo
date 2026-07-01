pipeline {
    agent any

    stages {
        stage('Run Shell Script') {
            steps {
                sh 'chmod +x demo.sh'
                sh './demo.sh'
            }
        }
    }

    post {
        success {
            emailext(
                to: 'YOUR_EMAIL@gmail.com',
                subject: "SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Hello,

Your Jenkins Pipeline has completed successfully.

Job Name    : ${env.JOB_NAME}
Build Number: ${env.BUILD_NUMBER}
Status      : SUCCESS

Build URL:
${env.BUILD_URL}

Regards,
Jenkins
"""
            )
        }

        failure {
            emailext(
                to: 'YOUR_EMAIL@gmail.com',
                subject: "FAILED: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Hello,

Your Jenkins Pipeline has failed.

Job Name    : ${env.JOB_NAME}
Build Number: ${env.BUILD_NUMBER}
Status      : FAILED

Build URL:
${env.BUILD_URL}

Regards,
Jenkins
"""
            )
        }
    }
}
