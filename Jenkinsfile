pipeline {
    agent any
    tools {
        jdk 'JDK'
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
                bat "mvn package -Dmaven.test.skip"
            }
        }
        stage('Create Zip') {
            steps {
                bat 'powershell Compress-Archive -Path ".\\target" -DestinationPath "target.zip"'
            }
        }
    }
}
