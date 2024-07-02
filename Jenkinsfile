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
                sh 'apt update'
                sh 'apt install -y libidn11-dev libicu-dev libjemalloc-dev'
                sh 'bundle install'
                sh 'bin/rubocop'
                sh 'bin/brakeman'
            }
        }
    }
}
