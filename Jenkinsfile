node {
    stage('scm') {
    git 'https://github.com/wakaleo/game-of-life.git'
    }
    stage('Build&package') {
        bat 'mvn package'
    }
    stage ('Result')
    {
        archive 'gameoflife-web/target/*.war'
        junit 'gameoflife-web/target/surefire-reports/*.xml'
    }
}