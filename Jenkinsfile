pipeline {
  agent any
  stages {
    stage('Retrieve Sources') {
      steps {
        echo workspace
        git(branch: 'main', url: 'https://github.com/BRSweagle/Icarus')
      }
    }

    stage('Config') {
      steps {
        SWEAGLEUpload(actionName: 'uploadProp', fileLocation: 'Components/Files/*.properties', format: 'properties', nodePath: 'Icarus', filenameNodes: true, withSnapshot: true, tag: '${BUILD_ID}')
        SWEAGLEUpload(actionName: 'uploadJSON', fileLocation: 'Components/Microservices/*.json', format: 'JSON', nodePath: 'Icarus', filenameNodes: true, withSnapshot: true, tag: '${BUILD_ID}')
        SWEAGLEUpload(actionName: 'uploadYAML', fileLocation: 'Components/Microservices/*.yaml', format: 'yaml', nodePath: 'Icarus', filenameNodes: true, withSnapshot: true, tag: '${BUILD_ID}')
        SWEAGLEUpload(actionName: 'uploadSpring', fileLocation: 'Components/Spring/*.properties', format: 'properties', nodePath: 'Icarus', filenameNodes: true, tag: '${BUILD_ID}', withSnapshot: true)
      }
    }

    stage('Test') {
      steps {
        echo 'Testing..'
        SWEAGLEValidate(actionName: 'Validate Tst-1', mdsName: 'Icarus.Tst-1', stored: true, markFailed: true, errMax: -1, warnMax: -1)
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }

  }
}