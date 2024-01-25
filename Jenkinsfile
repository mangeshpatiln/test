pipeline {
    agent any
        options {
        // This is required if you want to clean before build
        skipDefaultCheckout(true)
    }
    stages {
        stage('checkout') {
            steps {
                cleanWs()
                checkout scmGit(branches: [[name: '*/qa']], extensions: [], userRemoteConfigs: [[credentialsId: '5b9d84d5-d847-4e1a-aa96-54a82ffd472c', url: 'https://github.com/mangeshpatiln/test/']])
            }
        }
        stage('projectupdate') {
                        steps {
                    sh 'sed -i 's/seerportal_mangesh/seerportal_amit_3/g' sonar-project.properties'
                }
        }
        stage('sonarscan') {
                        steps {
                    sh '/home/jenkins_home/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/sonarscanner/bin/sonar-scanner -Dsonar.sources=. -Dsonar.host.url=http://192.168.0.25:9000 -Dsonar.login=squ_9f9d340ca218289a88edc3b822ad357d9dca58c2 -Dsonar.branch.name=$GIT_BRANCH'
                }
        }
    }
}

