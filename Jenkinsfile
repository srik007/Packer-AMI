pipeline {
  agent {
    docker {
      image 'goforgold/build-container'
    }

  }
  stages {
    stage('Create packer ami') {
      steps {
        sh 'packer build -var aws_access_key=${AWS_KEY} -var aws_secret_key=${AWS_SECRET_KEY} -var mongo_version=${MONGO_VERSION} -var version=${VERSION} -var base_ami=${BASE_AMI} -var region=${REGION} template.json'
      }
    }

  }
  environment {
    MONGO_VERSION = '4.2'
    REGION = 'ap-south-1'
    VERSION = '1.0'
    BASE_AMI = 'ami-0fd7e4b8e94538bef'
  }
}