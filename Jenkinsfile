pipeline {
    agent { docker {image 'maven:3.3.3'}
    }
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
        		sh 'echo "test stage"'
        	}
        }
        stage('Deploy-Staging') {
        	steps {
        		sh 'echo "deploy stage"'
        		sh './deploy staging'
        	}
        }
         stage('Deploy-Production') {
        	steps {
        		sh 'echo "deploy stage"'
        		sh './deploy production'
        	}
        }
    }
     post {
        always {
            echo 'Finished'
            deleteDir() /* clean up our workspace */
        }
        success {
            echo 'Success'
        }
        unstable {
            echo 'Unstable'
        }
        failure {
            echo 'Failed'
        }
        changed {
            echo 'Changed'
        }
    }
}