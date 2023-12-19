pipeline {
    agent any

    environment {
        SONAR_SCANNER_HOME = tool 'isaya'
        // Other environment variables...
    }

    stages {
        stage('SonarQube Analysis') {
            steps {
                script {
                    // Run the SonarQube Scanner analysis
                    sh "${SONAR_SCANNER_HOME}/bin/sonar-scanner -Dsonar.projectKey=mutuwa -Dsonar.sources=. -Dsonar.host.url=http://sonarqube:9000 -Dsonar.login=sqp_9c5c1aa15ac40284f359e279cecbc2da60e22473"
                }
            }
        }
        // Other stages...
    }

    post {
        success {
            echo 'SonarQube Analysis successful!'
        }
        failure {
            echo 'SonarQube Analysis failed!'
        }
    }
}
