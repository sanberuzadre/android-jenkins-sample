pipeline {
    agent any
    stages {
        stage('Pre-Build') {
            steps {
            echo "Let's go!"
            sh '''./gradlew --version'''
            echo "This is the end... my friend :)"
            }
        }
        stage('Build') {
            steps {
                echo "The build stage started..."
                sh '''./gradlew build'''
                echo "The build stage passed..."
            }
        }
        stage('Test') {
            steps {
                echo "The test stage started..."
                sh '''./gradlew check'''
                echo "The test stage passed..."
            }
        }
    }
    post {
        always {
            echo "The post-build stage started..."
            sh '''./gradlew clean'''
	        cleanWs()
            echo "The post-build stage passed..."
        }
    }
}
