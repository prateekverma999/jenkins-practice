pipeline {
    agent any

    environment {
        FILE = 'config.txt'
        FOLDER = 'build_dir'
    }

    stages {
        stage('Build') {
            steps {
                echo "Build process started..."
                script {
                    sh 'chmod +x build.sh'
                    sh './build.sh'
                    sh 'mkdir -p ./build_dir'
                }
                sh '''
                    echo "====== New laptop config ======" >> "$(FOLDER)/$(FILE)"
                    echo "motherbord" >> "$(FOLDER)/$(FILE)"
                '''
            }
        }
    }
}