pipeline {
    agent { docker 'maven:3.3.3' }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'javac HelloWorld.java'
                sh 'java HelloWorld'
            }
        }
        stage('test') {
        	steps{
        		sh 'make check'
        	}
        }
        stage('Deploy') {
        	steps {
        		sh 'make publish'
        	}
        }
    }
}