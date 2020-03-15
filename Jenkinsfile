pipeline {
    agent any
    stages {
        stage('Lint HTML') {
          steps {
            sh 'tidy -q -e *.html'
          }
        }
        stage('Upload to AWS') {
          steps {
            withAWS(region:'ap-northeast-1',credentials:'JenkinsUserAccessKey') {
              s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'udacity-cicd-silviaclaire')
            }
          }
        }
    }
}
