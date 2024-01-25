pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout scmGit(branches: [[name: '*/qa']], extensions: [], userRemoteConfigs: [[credentialsId: '5b9d84d5-d847-4e1a-aa96-54a82ffd472c', url: 'https://github.com/mangeshpatiln/test/']])
            }
        }
    }
}
