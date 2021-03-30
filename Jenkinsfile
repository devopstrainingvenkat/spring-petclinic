pipeline {
    agent any
    triggers {
        upstream(upstreamProjects: 'dummy', threshold: hudson.model.Result.SUCCESS)
    }
    stages{
        stage('Source'){
         steps{
             git 'https://github.com/devopstrainingvenkat/spring-petclinic.git'
         }
        }
        stage('Package'){
        steps{
            sh 'mvn package'
        }
        }
    }
}