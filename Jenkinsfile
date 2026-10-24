
pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/enirmo/SEDO-09-2026-Regular-Exam-2.git'
            }
        }

        stage('Restore') {
            steps {
                bat 'dotnet restore Homies.sln'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build Homies.sln --no-restore'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test Homies.sln --no-build'
            }
        }
    }
}
