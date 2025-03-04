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
                sh '''
                    mkdir -p ${FOLDER}
                    echo "====== New laptop config ======" >> ${FOLDER}/${FILE}
                    echo "motherboard" >> ${FOLDER}/${FILE}
                '''
            }
        }
    }
}
