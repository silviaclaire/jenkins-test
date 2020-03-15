pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
          steps {
            withAWS(region:'ap-northeast-1',credentials:'JenkinsUserAccessKey') {
              s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'udacity-cicd-silviaclaire')
            }
          }
        }
    }
}
