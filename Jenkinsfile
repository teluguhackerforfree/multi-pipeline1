pipeline {
    agent any

    stages {
        stage('source code for development') {
            steps {
                echo 'scm'
				git 'https://github.com/teluguhackerforfree/multidatapro.git'
            }
        }
		stage('compile') {
            steps {
                echo 'mvn compile'
				sh 'mvn compile'
            }
        }
		stage('package') {
            steps {
                echo 'mvn package'
				sh 'mvn package'
            }
        }
		stage('deploy') {
            steps {
                echo 'deployment'
				deploy adapters: [tomcat9(path: '', url: 'http://34.238.142.197:8081')], contextPath: 'dev', war: '**/*.war'
				
            }
        }
		
		
    }
}

