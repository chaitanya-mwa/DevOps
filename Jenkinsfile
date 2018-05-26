node {
    stage('scm') {
    git 'https://github.com/wakaleo/game-of-life.git'
    }
    
    stage('Build & Package') {
        withSonarQubeEnv('mysonar') {
            bat 'mvn clean package sonar:sonar'
        }
    }
    
   
}