pipeline {
  agent any

  stages {
    stage ('prepare Artifact') {
      steps{
       sh '''
         zip -r ../users.zip *
       '''
      }
    }
    stage('upload the artifact into nexus'){
      steps{
        sh '''
          curl -f -v -u admin:admin123 --upload-file ../users.zip http://172.31.2.243:8081/repository/users/users.zip

        '''

      }

    }

  }
}