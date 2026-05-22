pipeline {
    agent any

    environment {
        ANDROID_HOME = "C:\\Users\\SHUBAM CHOUDHARY\\AppData\\Local\\Android\\Sdk"
        JAVA_HOME = "C:\\Program Files\\Android\\Android Studio\\jbr"
    }

    stages {

        stage('Clean Project') {
            steps {
                bat 'gradlew clean'
            }
        }

        stage('Build APK') {
            steps {
                bat 'gradlew assembleDebug'
            }
        }

    }

    post {

        success {
            archiveArtifacts artifacts: 'app/build/outputs/**/*.apk'
            echo 'APK Build Successful!'
        }

        failure {
            echo 'APK Build Failed!'
        }
    }
}
