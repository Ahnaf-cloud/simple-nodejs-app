pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Mengambil kode dari GitHub...'
                checkout scm
            }
        }

        stage('Build Image') {   // BARU
            steps {   // BARU
                echo 'Membangun image Docker...'   // BARU
                sh 'docker build -t simple-app:$BUILD_NUMBER -t simple-app:latest .'   // BARU
            }   // BARU
        }   // BARU
    }

    post {
        success {
            echo "Build #${env.BUILD_NUMBER} berhasil."
        }
        failure {
            echo "Build #${env.BUILD_NUMBER} gagal. Periksa Console Output untuk melihat tahap yang bermasalah."
        }
    }
}
