pipeline {
    agent any

    environment {
        FILE = 'config.txt'
    }

    stages {
        stage('Build') {
            steps {
                echo "Build process started..."
                script {
                    sh chmod +x build.sh
                    sh ./build.sh
                    sh mkdir -p ./build_dir 
                    echo "====== New laptop config ======" >> build/$FILE
                    echo "motherbord" >> build_dir/$FILE
                }
            }
        }
    }
}