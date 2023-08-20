import groovy.util.*

pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Test') {
            agent {
                dockerfile {
                    dir 'cicd/xcode'
                    args '--network bridge'
                    reuseNode true
                }
            }
            steps {
                sh "xcodebuild test -project HelloWorld.xcodeproj -scheme HelloWorld -destination 'platform=iOS Simulator,name=iPhone 14,OS=16.4'"
            }
        }

    }
}
