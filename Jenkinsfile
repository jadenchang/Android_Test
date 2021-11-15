pipeline {
    agent {
        docker { image 'jadenchangtw/androidbuild:0.1' args '-u root' }
    }

    stages {
        stage('Build') {
            steps {
                sh 'gradle -PdisablePreDex assembleDebug'
            }
        }
    }
}