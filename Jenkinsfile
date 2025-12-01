pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Run PHP') {
            steps {
                powershell 'php index.php'
            }
        }
        stage('Unit Test') {
            steps {
                // Jalankan PHPUnit versi Composer di Windows
                powershell 'php vendor\\bin\\phpunit tests'
            }
        }
    }
    post {
        success {
            echo 'Pipeline sukses dijalankan!'
        }
        failure {
            echo 'Pipeline gagal!'
        }
    }
}
