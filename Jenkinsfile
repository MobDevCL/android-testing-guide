node {
    stage 'Checkout'
    checkout scm

    dir('SampleApp') {
        stage 'Compile'
        sh "./gradlew compileDebugSources"

        stage 'Test'
        sh "./gradlew test"

        stage 'Build'
        sh "./gradlew build"

        stage 'Release'
        archiveArtifacts artifacts: '**.apk', fingerprint: true
    }
}
