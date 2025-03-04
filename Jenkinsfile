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
                checkout scm
                echo "Build process started..."
                script {
                    sh 'chmod +x build.sh'
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
