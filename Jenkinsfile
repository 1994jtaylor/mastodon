pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr: '10', daysToKeepStr: '60'))
        parallelsAlwaysFailFast()
    }
    agent {
      docker {
        image "ruby"
      }
    }

    stages {
        stage('Hello') {
            steps {
                sh 'ruby -v'
            }
        }
    }
}
