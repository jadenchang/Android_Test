pipeline {
    agent {
        docker { image 'jadenchangtw/androidbuild:0.1' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'gradle --version'
            }
        }
    }
}