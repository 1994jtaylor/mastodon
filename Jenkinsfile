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
        stage('Lint') {
            steps {
                sh 'bundle install'
                sh 'bin/rubocop'
                sh 'bin/brakeman'
            }
        }
    }
}
