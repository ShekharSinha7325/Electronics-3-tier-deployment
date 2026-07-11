pipeline {
    agent {
        label 'electronix'
    }

    stages {
        stage("I am from Electronics") {
            steps {
                echo "Hello from Electronics"
            }
        }

        stage("Electronics Setup") {
            steps {
                echo "Electronics Setup is Working ✅"
            }
        }
    }

    post {
        success {
            echo "Pipeline Passed Successfully"

            mail(
                to: "shekharghura824@gmail.com",
                subject: "✅ SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Hello Team,

The Jenkins pipeline has completed successfully.

Build Details:
• Job Name      : ${env.JOB_NAME}
• Build Number  : ${env.BUILD_NUMBER}
• Build Status  : SUCCESS

Build URL:
${env.BUILD_URL}

This is an automated notification from Jenkins.

Regards,
Jenkins CI/CD
"""
            )
        }

        failure {
            echo "Pipeline Failed"

            mail(
                to: "info4work413@gmail.com",
                subject: "❌ FAILURE: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Hello Team,

The Jenkins pipeline execution has failed.

Build Details:
• Job Name      : ${env.JOB_NAME}
• Build Number  : ${env.BUILD_NUMBER}
• Build Status  : FAILURE

Please review the build logs and investigate the issue.

Build URL:
${env.BUILD_URL}

This is an automated notification from Jenkins.

Regards,
Jenkins CI/CD
"""
            )
        }

        
    }
}