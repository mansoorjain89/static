pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(credentials:'aws-static') {
                    def identity = awsIdentity()
                }
            }
        }
    }
}
