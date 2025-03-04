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
            cleanWs(patterns: [[pattern: '${FOLDER}/**', type: 'EXCLUDE']])
            archiveArtifacts '${FOLDER}/**'
        }
    }
}
