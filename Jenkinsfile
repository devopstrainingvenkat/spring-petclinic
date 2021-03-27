  
pipeline{
        agent any
        stages{
            stage('source'){
            steps{
                git 'https://github.com/devopstrainingvenkat/spring-petclinic.git'
            }
            }
            stage('package'){
            steps{
                sh 'mvn package'
                 }
             }
       }
} 
