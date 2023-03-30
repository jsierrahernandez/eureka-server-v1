node {
  stage("Git clone") {
    git branch: 'main', url: 'https://github.com/SoftwarDevelop3r/eureka-server-v1.git'
  }

  stage("Compilation") {
    sh "chmod +x -R ${env.WORKSPACE}"
    sh "mvn -N io.takari:maven:wrapper"
    sh "${env.WORKSPACE}/mvnw clean install -DskipTests"
  }
  
  stage('SonarQube analysis') {
    steps {
      script {
        // requires SonarQube Scanner 4.8+
        scannerHome = tool 'SonarQube Scanner 4.8'
      }
      withSonarQubeEnv('SonarQube Scanner') {
        sh "${scannerHome}/bin/sonar-scanner"
      }
    }
  }

  stage("Deployment") {
    sh 'sudo systemctl stop eureka'
    sh 'sudo cp target/eureka-0.0.1-SNAPSHOT.jar /home/x658888/production/bin/'
    sh 'sudo systemctl start eureka'
   }

}
