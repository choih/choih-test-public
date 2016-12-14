
timestamps 
{
  node('choih-test')
  {
    checkout scm
    sh 'rm -f ~/.docker/config.json ~/.dockercfg'
    docker.withRegistry('choih/ubuntu-git-ssh:16',choih-test) {}
    docker.image("choih/ubuntu-git-ssh:16").pull()
    docker.image("choih/ubuntu-git-ssh:16").inside('-v /tmp:/tmp')
    {
      sh 'ls -la'
    }
  }
}
