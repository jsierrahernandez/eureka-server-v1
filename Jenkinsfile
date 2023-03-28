node {
  stage("Clone the project") {
    git branch: 'main', url: 'https://github.com/SoftwarDevelop3r/eureka-server-v1.git'
  }

  stage("Compilation") {
    sh "chmod +x -R ${env.WORKSPACE}"
    sh "mvn -N io.takari:maven:wrapper"
    sh "${env.WORKSPACE}/mvnw clean install -DskipTests"
  }

  //stage("Deployment") {
    //stage("Deployment") {
      //sh 'nohup ./mvnw spring-boot:run -Dserver.port=8001 &'
    //}
  //}
}
