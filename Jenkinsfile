node{
  stage('SCM Checout'){
   
  git 'https://github.com/sidharthvijayakumar/FinalWar'
  }
  stage('Build'){
     def mvnHome = tool name: 'Maven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean package"
  }
  stage("publish to s3") {
      
  s3Upload(file:'/var/lib/jenkins/workspace/WarPipeline/target/sparkjava-hello-world-1.0.war', bucket:'s3artifactsforjenkins', path:'target')
    
  } 
}
