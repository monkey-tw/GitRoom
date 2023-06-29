pipeline {
    agent any

    environment {
        // Setup Ruby to PATH
        RUBY_HOME = "/usr/local/opt/ruby"
        PATH = "$RUBY_HOME/bin:$PATH"
        LANG = "en_US.UTF-8"
    }

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
                    sh "pwd"
                    sh "echo $SHELL"
                    sh "which ruby"
                    sh "which gem"
                    // sh '/usr/local/opt/ruby/bin/gem install bundler'
                    sh "bundle install"
                    sh "bundle exec fastlane beta"
                }
            }
        }
    }
}
