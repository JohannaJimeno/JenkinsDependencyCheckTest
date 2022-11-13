pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                git '/home/onedrive/documents/github/JenkinsDependencyCheckTest'
            }
        }

        stage('OWASP DependencyCheck') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
            }
        }
    }
    post {
        success {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}
