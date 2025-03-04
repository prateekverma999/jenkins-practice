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
            archiveArtifacts '${FOLDER}/**'
            cleanWs(patterns: [
                    [pattern: '${FOLDER}/**', type: 'EXCLUDE'],
                    [pattern: '.git', type: 'INCLUDE']
                ]
            )
        }
    }
}
