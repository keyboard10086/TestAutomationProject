pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "${BUILD_URL}"
            }
        }
        stage('Test') {
            steps {
                echo "${NODE_NAME}"
            }
        }
        stage('Deploy') {
            environment{
                CC = """
                    ${sh(
                        returnStdout: true,
                        script: 'echo "abcdefg"'

                    )}
                """
                DD = """
                    ${sh(
                        returnStatus: true,
                        script: 'exit 0'
                    )}
                """

            }
            steps {
                echo 'Deploying....'
                sh 'echo "${CC}"'
                sh 'echo "${DD}"'
            }
        }
    }
}