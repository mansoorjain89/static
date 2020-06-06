pipeline {
    agent any
    stages {

        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
                sh 'echo "All linting checks passed"'
            }
        }

        stage('Upload to AWS') {
            steps {
                withAWS(credentials: 'aws-static', region: 'us-east-2') {
                    s3Upload(file:'index.html', bucket:'bucketforjenkins', path:'index.html')
                }
            }
        }
    }
}
