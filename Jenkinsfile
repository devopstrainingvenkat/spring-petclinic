pipeline {
    agent any
    triggers {
        upstream(upstreamProjects: 'sample1', threshold: hudson.model.Result.SUCCESS)
    }
    stages{
        stage('Source'){
         steps{
                  checkout([$class: 'GitSCM',
        branches: [[name: '*/declarativetrigger']],
        extensions: [[$class: 'CloneOption', timeout: 120]],
        gitTool: 'Default',
        userRemoteConfigs: [[url: 'https://github.com/devopstrainingvenkat/spring-petclinic.git']]
    ])
         }
        }
        stage('Package'){
        steps{
            sh 'mvn package'
        }
        }
    }
}
