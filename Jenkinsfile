pipeline {
    agent any

    environment {
        FILE = 'config.txt'
        FOLDER = 'build_dir'
    }

    stages {
        stage('Build') {
            steps {
                cleanWs()
                echo "Build process started..."

                script {
                    // Ensure build.sh exists before setting permissions
                    sh '[ -f build.sh ] && chmod +x build.sh || echo "build.sh not found!"'
                }

                sh '''
                    ./build.sh
                    mkdir -p ${FOLDER}
                    echo "====== New laptop config ======" >> ${FOLDER}/${FILE}
                    echo "motherboard" >> ${FOLDER}/${FILE}
                '''
            }
        }
    }
}
