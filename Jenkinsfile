pipeline {
    agent any

    stages {
        stage('Continous-Download') {
            steps {
                git 'https://github.com/sunildevops77/maven.git'
            }
        }
         stage('continous-Build') {
            steps {
                sh 'mvn package' 
            }
        }
		stage('Continous-Testing') {
            steps {
                echo 'Continuous-Testing ' 
            }
        }
        stage('archive-Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false 
            }
        }
		stage('Continous-deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '69b801ab-7f37-4497-a9f1-f6a48fc5afc5', path: '', url: 'http://3.6.86.43:8080//')], contextPath: 'multibranchenv', war: '**/*.war'
            }
        }
    }
}
