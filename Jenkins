pipeline {
    agent any

    stages {
        stage('Checkout') {   // BARU
            steps {
                echo 'Mengambil kode dari GitHub...'
                checkout scm
            }
        }
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
