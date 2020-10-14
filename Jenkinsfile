node{
  stage('SCM Checout'){
   
  git 'https://github.com/sidharthvijayakumar/FinalWar'
  }
  stage('Build'){
     def mvnHome = tool name: 'Maven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean install"
  }
}
