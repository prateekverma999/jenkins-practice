pipeline {
    agent any

    environment {
        FILE = config.txt
    }

    stages {
        stage('Build') {
            steps {
                scripts {
                    ./build.sh
                }
            }
        }
    }
}