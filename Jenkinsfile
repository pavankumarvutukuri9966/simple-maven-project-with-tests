pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Build') {
            steps {

                git 'https://github.com/pavankumarvutukuri9966/simple-maven-project-with-tests.git'


                sh "mvn -Dmaven.test.failure.ignore=true clean package"


            }
        }

            post {

                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }

        }
}
