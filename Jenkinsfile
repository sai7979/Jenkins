pipeline {
    agent any
    tools {
        jdk 'JAVA_HOME'
        maven 'MAVEN_HOME'
    }


    stages {
        stage('GitHub project pull') {
            steps {
                git branch: 'main', url: 'https://github.com/sai7979/jenkins.git'
            }
            
        }
        stage('mavenbuild'){
            steps {
                sh "mvn package -Dmaven.test.skip"
            }
        }
        stage('Create Zip') {
            steps {
                sh "zip -r target.zip target"
            }
        }
    }
}
