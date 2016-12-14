timestamps 
{
  node('cloud&&centos')
  {
    checkout scm
    sh 'rm -f ~/.docker/config.json ~/.dockercfg'
    docker.withRegistry('https://autodesk-docker-build-images.art-bobcat.autodesk.com:10873/','art-bobcat_service_account_id') {}
    docker.image("${imageName}").pull('autodesk-docker-build-images.art-bobcat.autodesk.com:10873/ubuntu-git-ssh:16')
    docker.image("${imageName}").inside('-v /tmp:/tmp')
    {
      sh 'ls -la'
    }
    sh 'docker rmi $(docker images -q)'
  }
}
