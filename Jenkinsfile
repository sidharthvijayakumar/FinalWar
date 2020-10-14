node{
  stage('SCM Checout'){
   
  git 'https://github.com/sidharthvijayakumar/FinalWar'
  }
  stage('Build'){
     def mvnHome = tool name: 'Maven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean package"
  }
  stage("publish to s3") {
      
  s3Upload(file:'/var/lib/jenkins/workspace/wwpDeploy/target/wwp-1.0.0.war', bucket:'s3artifactsforjenkins', path:'target')
    
  } 
  stage("Deploy"){
    sshagent(['tomcat']) {
    sh "scp -o StrictHostKeyChecking=no target/*.war ec2-user@18.220.23.127:/home/ec2-user/tomcat/webapps"
  }
}
