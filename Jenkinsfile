pipeline {
    agent {
        docker { image 'jadenchangtw/androidbuild:0.1' }
    }

    stages {
        stage('Build') {
            steps {
                sh 'gradlew assembleDebug'
            }
        }
    }
}