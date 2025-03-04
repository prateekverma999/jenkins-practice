pipeline {
    agent any

    environment {
        FILE = 'config.txt'
        FOLDER = 'build'
    }

    stages {
        stage('Build') {
            steps {
                cleanWs()
                checkout scm
                echo "Build process started..."
                script {
                    sh 'chmod +x build.sh'
                    sh './build.sh'
                }
            }
        }
    }
    post {
        success {
            archiveArtifacts "${FOLDER}/**"
            script {
                sh '''
                    find . -mindepth 1 -maxdepth 1 ! -name "${FOLDER}" ! -name '.git' -exec rm -rf {} +
                '''
            }
        }
    }
}
