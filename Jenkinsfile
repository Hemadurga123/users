pipeline {
  agent {
    label 'NODEJS'
  }

  stages {
    stage ('preparing the Artifact') {
      steps{
       sh '''
         zip -r ../users.zip *
       '''
      }
    }
    stage('upload the artifact into nexus'){
      steps{
        sh '''
          curl -f -v -u admin:admin123 --upload-file ../users.zip http://172.31.10.228:8081/repository/users/users.zip

        '''

      }

    }

  }
}