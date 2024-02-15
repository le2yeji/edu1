node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("yyazi/edu1")
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'docker_ci') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
 }
