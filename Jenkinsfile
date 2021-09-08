pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/hongj0a/GitOps will replace by sed command before RUN
        git url: 'https://github.com/hongj0a/GitOps', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}