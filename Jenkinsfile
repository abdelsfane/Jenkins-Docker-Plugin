node {
  checkout scm
  
  stage("Update") {
      sh '''
      echo "Hello!"
        sudo apt-get update -y
        '''
  }
  stage("Install") {
      sh '''
        sudo apt-get install \
            apt-transport-https \
            ca-certificates \
            curl \
            software-properties-common -y
        '''
  }
  stage("Curl") {
      sh '''
        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
        '''
  }
  stage("Fingerprint") {
      sh '''
        sudo apt-key fingerprint 0EBFCD88 -y
        '''
  }
  stage("Get Repo") {
      sh '''
        sudo add-apt-repository \
           "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
           $(lsb_release -cs) \
           stable -y"
        '''
  }
  stage("Update") {
      sh '''
        sudo apt-get update -y
        '''
  }
  stage("Run Apt-Get") {
      sh '''
        sudo apt-get install docker-ce -y
        '''
  }
  stage("Run Docker") {
      sh '''
        docker
        '''
  }

}
