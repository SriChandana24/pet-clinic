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
        
        stage ('Deploy') {
            steps {
                sh 'ansible-playbook -i inv.ini main.yml'
            }
        }
    }
}
