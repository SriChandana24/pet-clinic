pipeline {
    
    agent {
            label 'test'
        } 
    
    stages {
        stage('SonarQube Analysis') {
            steps{
                withSonarQubeEnv('sonarqube-9.5') {
                sh "mvn sonar:sonar"
                 
                }
            }
            
            
        stage ('test Stage') {

            steps {                
                    sh 'mvn test'                
            }
        }
        stage ('Compile Stage') {

            steps {                
                    sh 'mvn clean compile'                
            }
        }
        
        stage ('Build') {
            steps {                
                    sh 'mvn package'                
            }
        }
                
    }

    post {
            always {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
                junit 'target/surefire-reports/*.xml'
            }
        }
}
