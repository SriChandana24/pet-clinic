pipeline {
    agent any
    stages {
        stage('Git checkout'){
            steps{
                git branch: 'dev', url: 'https://github.com/SriChandana24/pet-clinic.git'
        }
        
        /*stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn clean compile'
                }
            }
        }
        
        stage ('Build') {
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn package'
                }
            }
        }
        
        stage ('Deploy') {
            steps {
                sh 'ansible-playbook -i inv.ini main.yml'
            }
        }*/
    }
}
