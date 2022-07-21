pipeline {
    agent {
        docker {
            image 'zenika/alpine-maven'  
        }
    }
    stages {
            stage('Build') {
                steps {
                    sh 'mvn -B -DskipTests clean package'
                }
            }
            stage('test') {
                steps {
                    sh 'mvn test'
                }
            }
            stage(run) {
                steps {
                    sh 'java -jar /var/jenkins_home/workspace/pipeline-maven/target/*.jar'
                }
            }


    }

}