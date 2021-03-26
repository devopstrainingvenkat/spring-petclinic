 node ('MASTER') {
    stage ('scm'){
        git 'https://github.com/devopstrainingvenkat/spring-petclinic.git'
    }

    stage ('build'){
        sh 'mvn package'
    }
}
