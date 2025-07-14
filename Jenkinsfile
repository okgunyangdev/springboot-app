pipeline {
    agent any

    tools {
        jdk 'Zulu-17'
        gradle 'Gradle-8'
    }

    environment {
        DB_HOST = 'localhost'
        DB_NAME = 'myapp'
        DB_USER = 'jenkins'
        DB_PASS = 'jenkins123'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/okgunyangdev/springboot-app.git'
            }
        }

        stage('Build') {
            steps {
                gradle 'clean build'
            }
        }

        stage('Test') {
            steps {
                gradle 'test'
            }
        }

        stage('Run') {
            steps {
                bat 'start java -jar build\\libs\\*.jar'
            }
        }
    }
}