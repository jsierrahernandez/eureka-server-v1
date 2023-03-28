node {
  stage("Clone the project") {
    git branch: 'main', url: 'https://github.com/SoftwarDevelop3r/eureka-server-v1.git'
  }

  stage("Compilation") {
    sh "chmod +x -R ${env.WORKSPACE}"
    sh "mvn -N io.takari:maven:wrapper"
    sh "${env.WORKSPACE}/mvnw clean install -DskipTests"
  }

  stage("Deployment") {
    stage("Deployment") {
      sh 'sudo systemctl stop eureka
      sh 'cp target/eureka-0.0.1-SNAPSHOT.jar /home/x658888/production/bin/'
      sh 'sudo systemctl start eureka
    }
  }
}
