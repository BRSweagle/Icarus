pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }

        stage('Config') {
            stage('Config') {
              steps {
                SWEAGLEUpload(actionName: 'uploadConfig', fileLocation: '/Components/Files', format: 'properties', nodePath: 'Icarus,Components,Files', subDirectories: true, tag: '${BUILD_ID)', autoRecognize: true, withSnapshot: false)
            }

        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
