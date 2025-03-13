pipeline {
    agent {
        label 'Slave1'
    }

    stages {
        stage('git-repo') {
            steps {
                git branch:'master', url:'https://github.com/kliakos/sparkjava-war-example'
            }
        }
        stage('mvn') {
            steps {
                sh '/home/ubuntu/apache-maven-3.9.9/bin/mvn clean package'
            }
        }
        stage('tomcat-stage') {
            steps {
                sh 'rm -r /home/ubuntu/apache-tomcat-9.0.102/webapps/sparkjava-hello-world-1.0"
                sh 'cp /home/ubuntu/jenkins/workspace/Job1/target/sparkjava-hello-world-1.0.war /home/ubuntu/apache-tomcat-9.0.102/webapps/'
            }
        }
    }
}
