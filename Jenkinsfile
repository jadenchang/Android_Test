pipeline {
    agent {
        docker {
        image 'jadenchangtw/androidbuild:0.1'
        args '-u root:root'
        }
    }

    stages {

        stage('SonarQube Analysis') {
            when {
                expression {
                    return GIT_BRANCH ==~ "^(?i)(develop|main|master|release.*|task.*|bugfix.*|story.*|feature.*|pr-\\d+)\$"
                }
            }

            steps {
               sh 'printenv'
               withSonarQubeEnv('SonarQube Server') {
                    script {
                        if ((GIT_BRANCH == 'develop')||(GIT_BRANCH == 'main')||(GIT_BRANCH == 'master')) {
                           sh 'mvn sonar:sonar'
                        }
                    }
               }
        }

        stage('Build') {
            steps {
                sh 'gradle -PdisablePreDex assembleDebug'
            }
        }
    }


}