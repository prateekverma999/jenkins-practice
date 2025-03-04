pipeline {
    agent any

    environment {
        FILE = 'config.txt'
    }

    stages {
        stage('Build') {
            steps {
                echo "Build process started..."
                scripts {
                    sh './build.sh'
                    echo "====== New laptop config ======" >> build/$FILE
                    echo "motherbord" >> build/$FILE
                }
            }
        }
    }
}