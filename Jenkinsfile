pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
        disableConcurrentBuilds()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            steps {
                bat 'dotnet restore SoftUniBazar.sln'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build SoftUniBazar.sln --configuration Release --no-restore'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test SoftUniBazar.sln --configuration Release --no-build'
            }
        }
    }
}