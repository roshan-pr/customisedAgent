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
                    args                 '-v /tmp:/tmp'
                }
            }
            steps {
                sh 'cpplint --help'
            }
        }
    }
}
