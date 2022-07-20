pipeline {
    
    agent {
            label 'test'
        } 
    
    stages {
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
