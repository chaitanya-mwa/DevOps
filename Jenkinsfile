node {
    stage('scm') {
    git 'https://github.com/khoubyari/spring-boot-rest-example.git'
    }
    
    stage('Build & Package') {
        withSonarQubeEnv('mysonar') {
            bat 'mvn clean package sonar:sonar'
        }
    }
    
   
}