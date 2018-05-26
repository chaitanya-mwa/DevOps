node {
    stage('scm') {
    git 'https://github.com/wakaleo/game-of-life.git'
    }
    stage('Build&package') {
        bat 'mvn package'
    }
    stage('Build & Package') {
        withSonarQubeEnv('mysonar') {
            bat 'mvn clean package sonar:sonar'
        }
    }
    
    stage("Quality Gate") {
        timeout(time: 1, unit: 'HOURS') {
              def qg = waitForQualityGate()
              if (qg.status != 'OK') {
                  error "Pipeline aborted due to quality gate failure: ${qg.status}"
              }
          }
    }
}