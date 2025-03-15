pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Alone-wolf-sudo/cicd_pipeline.git'
            }
        }
        stage('Run Python Script') {
            steps {
                script {
                    def pythonHome = tool name: 'Python 3', type: 'Python'
                    withEnv(["PATH+PYTHON=${pythonHome}/bin"]) {
                        dir('regression_test') {
                            sh 'python main.py'
                        }
                    }
                }
            }
        }
    }
}