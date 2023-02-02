pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Git Pull') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/krishnananda1989/hello-world.git'
            }
        }
        stage('Maven Build') {
            steps {
                // Get some code from a GitHub repository
                sh 'mvn install package'
            }
        }
        stage('Docker Build') {
            steps {
                // Get some code from a GitHub repository
                sh 'sudo docker build -t krishna_parida .'
            }
        }
        stage('Docker run') {
            steps {
                // Get some code from a GitHub repository
                //sh 'sudo docker stop Krishnap'
                //sh 'sudo docker rm Krishnap'
                sh 'sudo docker run -itd -p 8081:8080 --name Krishnap krishna_parida'
            }
        }
//        stage('Deploy To Tomcat') {
//            steps {
                // Get some code from a GitHub repository
//                deploy adapters: [tomcat9(credentialsId: 'cb60f3f4-9843-4b55-9027-65323c079e00', path: '', url: 'http://34.125.136.16:8080/')], contextPath: null, war: 'webapp/target/webapp.war'
//            }
//        }
    }
}
