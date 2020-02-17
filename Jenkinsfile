pipeline {
    agent any
    stages {
        stage ('CBuilding') {

            steps {
                withMaven(maven : 'maven_project') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Testing') {

            steps {
                withMaven(maven : 'maven_project') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Install Stage') {
            steps {
                withMaven(maven : 'maven_project') {
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
