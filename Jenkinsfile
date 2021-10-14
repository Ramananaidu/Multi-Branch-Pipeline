pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                mvn_version = 'M2_HOME'
                withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                     //sh "mvn clean package"
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven-3.6.3') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven-3.6.3') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
