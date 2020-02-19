pipeline {
    agent any
    stages {
        stage ('CBuilding') {

            steps {
                withMaven(maven : 'maven-project-3.6.3') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Testing') {

            steps {
                withMaven(maven : 'maven-project-3.6.3') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Install Stage') {
            steps {
                withMaven(maven : 'maven-project-3.6.3') {
                    sh 'mvn install'
                }
            }
        }
    }
     post {
        
        success {
            echo "Build ejecutado correctamente"
        }
        failure {
            echo "Fallo en compilacion"
        }
    }
}
