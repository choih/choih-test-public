properties([pipelineTriggers([cron('* * * * *')])]) // run every minute

timestamps 
{
  node('choih-test')
  {
    checkout scm
    docker.withRegistry('','choih-test') {}
    docker.image("choih/ubuntu-git-ssh:16").pull()
    docker.image("choih/ubuntu-git-ssh:16").inside('-v /tmp:/tmp')
    {
      sh 'ls -la'
    }
  }
}
