pipeline{
    agent{label 'MAY_17'}
    stages{
        stage(vcs){
            steps{
                git url: 'https://github.com/declarativepipeline/game-of-life.git'
                branch: 'scm'
            }
        }
        stage(build){
            steps{
                sh 'java -version'
                sh 'mvn --version'
                sh 'mvn compile'
                sh 'mvn test'
                sh 'mvn package'
            }
        }
        stage(artifact){
            steps{
                archiveArtifacts artifacts: '**/target/*.war'
            }
        }
    }
}