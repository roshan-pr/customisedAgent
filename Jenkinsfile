pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    stage('Lint') {
            agent {
                // Equivalent to "docker build -f Dockerfile.cpplint ./scripts/
                dockerfile {
                    filename             'Dockerfile.cpplint'
                    dir                  'scripts'
                    label                'cppLintImage'
                }
            }
            steps {
                sh 'cpplint --help'
            }
        }
    }
}
