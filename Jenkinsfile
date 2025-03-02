pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/MUKERA-NITHISHA/Arduino-CI-CD.git'
            }
        }

        stage('Install Arduino CLI') {
            steps {
                sh 'curl -fsSL https://raw.githubusercontent.com/arduino/arduino-cli/master/install.sh | sh'
            }
        }

        stage('Compile Sketch') {
            steps {
                sh 'arduino-cli compile --fqbn arduino:avr:uno smart_light.ino'
            }
        }

        stage('Upload to Arduino') {
            steps {
                sh 'arduino-cli upload -p /dev/ttyUSB0 --fqbn arduino:avr:uno smart_light.ino'
            }
        }
    }
}
