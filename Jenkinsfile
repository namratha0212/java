pipeline {
    agent any

    stages {
        stage('Cloning Java Repository') {
            steps {
                git 'https://github.com/Sharath-yp25/java.git'
            }
        }

        stage('Compile and Execute Java Project') {
            steps {
                bat '''
                    javac Test.java
                    java Test
                '''
            }
        }
    }

    post {
        success {
            mail(
                to: 'sidhu2222005@gmail.com',
                cc: 'sidharth2222005@gmail.com',
                subject: 'Build Success',
                body: 'Build completed successfully. Thank you.'
            )
        }

        failure {
            mail(
                to: 'sidhu2222005@gmail.com',
                subject: 'Build Failed',
                body: 'The Jenkins build has failed. Please check the console output.'
            )
        }
    }
}
