 node {
    stage ('scm'){
     
      checkout([$class: 'GitSCM',
        branches: [[name: '*/main']],
        extensions: [[$class: 'CloneOption', timeout: 120]],
        gitTool: 'Default', 
        userRemoteConfigs: [[url: 'https://github.com/devopstrainingvenkat/spring-petclinic.git']]
    ])
     
    }

    stage ('build'){
        sh 'mvn package'
    }
  
    stage('Code Quality Check via SonarQube') {
   steps {
       script {
       def scannerHome = tool 'sonarqube';
           withSonarQubeEnv("sonarqube") {
           sh "${tool("sonarqube")}/opt/sonar_scanner \
           -Dsonar.projectKey=test \
           -Dsonar.projectName=test \
           -Dsonar.projectVersion=1.0 \
           -Dsonar.sources=src/main/java/ \
           -Dsonar.language=java \
           -Dsonar.sourceEncoding=UTF-8 \
           -Dsonar.java.binaries=target/classes \
           -Dsonar.host.url=http://3.131.13.136:9000 \
           -Dsonar.login=jenkins"
               }
           }
       }
   }
}
