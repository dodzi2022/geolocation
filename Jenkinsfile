pipeline {
    agent any
    tools {
       maven "M2_HOME"
     }
    withSonarQubeEnv {
    // some block
        sonar.projectKey=dodzi2022_geoMVPX0
        sonar.organization=dodzi2022
        sonar.host.url=https://sonarcloud.io
        sonar.login=8739b5ca19d023862eb4539e1cdb59a48e682cac
        sonar.sources=src
        sonar.java.binaries=.
}

    stages {
        stage('Build') {
            steps {
               sh "mvn clean"
               sh "mvn install"
               sh "mvn package"
            }
        }
        stage('Test') {
            steps {
                sh "mvn test"
        }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy step'
                sleep 10
            }
        }
        stage('Docker') {
            steps {
                echo 'Image step'
            }
        }
    }
}
    
