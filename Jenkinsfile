node ('master') {

  stage ('SCM-checkout') {
    checkout([$class: 'GitSCM', 
       branches: [[name: '*/master']], 
       extensions: [], 
       userRemoteConfigs: [[url: 'https://github.com/plusforum/helloworldweb.git']]])
  }
  
  stage ('build') {
    sh 'mvn clean install'
  }
  
  stage ('archive') {
    archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
  }
  
}
