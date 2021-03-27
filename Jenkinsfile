  
pipeline{
        agent any
        stages{
            stage('source'){
            steps{
                checkout([$class: 'GitSCM',
        branches: [[name: '*/main']],
        extensions: [[$class: 'CloneOption', timeout: 120]],
        gitTool: 'Default',
        userRemoteConfigs: [[url: 'https://github.com/devopstrainingvenkat/spring-petclinic.git']]
    ])
            }
            }
            stage('package'){
            steps{
                sh 'mvn package'
                 }
             }
       }
} 
