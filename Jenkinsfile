pipeline {
    agent any

    parameters {
        choice(
            description: 'choice test',
            name: 'choice demo',
            choices: ['aaa', 'bbb']
        )
        
        string(
            description: "string test",
            name: "INPUT_NAME",
            defaultValue: "haha"
        ) 
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage("clean") {
            steps {
                // xcodebuild clean -project GitRoom -scheme GitRoom -configuration ${GITROOM_CONFIG}
                echo "xcodebuild clean ${env.GITROOM_CONFIG} successfully 1"
                echo "xcodebuild clean ${GITROOM_CONFIG} successfully 2"
            }
        }
        
        stage("build") {
            steps {
                script {
                    //sh "xcodebuild -project GitRoom.xcodeproj -scheme GitRoom -configuration ${GITROOM_CONFIG} -sdk iphoneos -derivedDataPath build -archivePath build/GitRoom.xcarchive build"
                    echo "build ok"
                }
            }
        }

        stage("fastlane") {
            steps {
                script {
                    sh "echo $SHELL"
                    sh "which ruby"
                    sh "which gem"
                    sh '/usr/local/opt/ruby/bin/gem install bundler'
                    sh "/usr/local/opt/ruby/bin/bundle install"
                    sh "/usr/local/opt/ruby/bin/bundle exec fastlane beta"
                }
            }
        }
    }
}
