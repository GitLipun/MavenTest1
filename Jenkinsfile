pipeline {
    tools{
       jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
    agent any

    stages {
        stage('git checkout') {
            steps {
                git 'https://github.com/GitLipun/MavenTest1.git'
            }
        }
        stage('compile') {
            steps {
               bat 'mvn compile'
            }
        }
        stage('test'){
            steps {
               bat 'mvn test'
            }
        }
            stage('package') {
                steps {
               	 sh 'mvn clean package'
                 sh "mv target/*.jar target/myapp.jar"
            }
        }
        
    }
}

