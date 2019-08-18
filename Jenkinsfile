node {
  checkout scm
  
  stage("Update") {
      sh '''
      echo "Hello!"
        sudo apt-get update
        '''
  }
  stage("Install") {
      sh '''
        sudo apt-get install \
            apt-transport-https \
            ca-certificates \
            curl \
            software-properties-common
        '''
  }
  stage("Curl") {
      sh '''
        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
        '''
  }
  stage("Fingerprint") {
      sh '''
        sudo apt-key fingerprint 0EBFCD88
        '''
  }
  stage("Get Repo") {
      sh '''
        sudo add-apt-repository \
           "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
           $(lsb_release -cs) \
           stable"
        '''
  }
  stage("Update") {
      sh '''
        sudo apt-get update
        '''
  }
  stage("Run Apt-Get") {
      sh '''
        sudo apt-get install docker-ce
        '''
  }
  stage("Run Docker") {
      sh '''
        docker
        '''
  }

}
