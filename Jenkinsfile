pipeline {
    agent any
    environment {
       def mvn_version = 'M2_HOME'

    stages {
        stage ('Compile Stage') {

            steps {
                
                withEnv(maven : 'maven_3_8_2') {
                     //sh "mvn clean package"
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_8_2') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_8_2') {
                    sh 'mvn deploy'
                }
            }
        }
    }
  }
}
