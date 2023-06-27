pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage("clean") {
            steps {
                // xcodebuild clean -project GitRoom -scheme GitRoom -configuration ${GITROOM_CONFIG}
                //echo "xcodebuild clean ${env.GITROOM_CONFIG} successfully 1"
                //echo "xcodebuild clean ${GITROOM_CONFIG} successfully 2"
                echo "clean ok"
            } 
        }
    }
}
