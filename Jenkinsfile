pipeline {
    tools{
        jdk 'JAVA_HOME'
        maven'M2_HOME'
    }
    agent {label 'linuxslv'}

    stages {
        stage('git checkout') {
            steps {
                git 'https://github.com/GitLipun/MavenTest1.git'
            }
        }
        stage('compile') {
            steps {
               sh 'mvn compile'
            }
        }
        stage('test'){
            steps {
               sh 'mvn test'
            }
        }
            stage('package') {
                steps {
               sh 'mvn package'
            }
        }
        
    }
}

