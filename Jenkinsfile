pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Dependencies') {
            steps {
                sh '/usr/local/bin/pod install'
            }
        }

        stage('Test') {
            steps {
                sh "xcodebuild test -project HelloWorld.xcodeproj -scheme HelloWorld -destination 'platform=iOS Simulator,name=iPhone 14,OS=16.4'"
            }
        }

    }
}
