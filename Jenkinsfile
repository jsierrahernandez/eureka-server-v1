node {
  stage("Clone the project") {
    git branch: 'main', url: 'https://github.com/SoftwarDevelop3r/eureka-server-v1.git'
  }

  stage("Compilation") {
    sh "./mvnw -f eureka-server/pom.xml clean install -DskipTests"
  }

  //stage("Deployment") {
    //stage("Deployment") {
      //sh 'nohup ./mvnw spring-boot:run -Dserver.port=8001 &'
    //}
  //}
}
