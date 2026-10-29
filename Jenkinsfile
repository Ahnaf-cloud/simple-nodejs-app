pipeline {
    agent any

    environment {   // BARU
        REGISTRY   = '192.168.10.10:5000'   // BARU
        IMAGE_NAME = 'simple-app'   // BARU
    }   // BARU

    stages {
        stage('Checkout') {
            steps {
                echo 'Mengambil kode dari GitHub...'
                checkout scm
            }
        }

        stage('Build Image') {
            steps {
                echo 'Membangun image Docker...'
                sh 'docker build -t $REGISTRY/$IMAGE_NAME:$BUILD_NUMBER -t $REGISTRY/$IMAGE_NAME:latest .'   // DIUBAH
            }
        }

        stage('Push to Registry') {   // BARU
            steps {   // BARU
                echo 'Mengirim image ke registry lokal...'   // BARU
                sh 'docker push $REGISTRY/$IMAGE_NAME:$BUILD_NUMBER'   // BARU
                sh 'docker push $REGISTRY/$IMAGE_NAME:latest'   // BARU
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
