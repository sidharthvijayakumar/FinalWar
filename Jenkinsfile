node{
  stage('SCM Checout'){
   
  git 'https://github.com/sidharthvijayakumar/FinalWar.git'
  }
  stage('Build'){
     def mvnHome = tool name: 'Maven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean package"
  }
}
