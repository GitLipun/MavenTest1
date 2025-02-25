pipeline {
    tools{
        jdk 'JAVA_HOME_WIN'
        maven'M2_HOME_WIN'
    }
    agent {winslave}

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
               bat 'mvn package'
            }
        }
        
    }
}
