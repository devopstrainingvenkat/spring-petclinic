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
}
