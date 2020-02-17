pipeline {
    agent {node {label 'master'} }
    stages {
        stage('Environment') {
            agent { 
                label 'master'
            }
            steps {
		echo "NODE_NAME = ${env.NODE_NAME}"
		sh 'printenv'
            }
        }
        stage('Build') {
            agent { 
                label 'ZSbuild'
            }
            steps {
                  echo "NODE_NAME = ${env.NODE_NAME}"
                  sh 'hostname -i'
                  sh 'echo "Build Started"'			
                  sh 'pwd'
            }
        }
        stage('Customer Server1') {
            agent { 
                // node 'ZSstage1'
                label 'ZScustomer'
            }
            steps {
                echo "NODE_NAME = ${env.NODE_NAME}"
                sh 'hostname -i'
	       sh 'pwd'
            }
            post {
                always {
                    sh 'echo "Post Test on Linux ZSstage"'
                    sh 'echo "Check the Jenkins Page here http://ec2-54-86-91-68.compute-1.amazonaws.com:8080/jenkins"'
                }
            }
        }

       stage('Customer Server2') {
            agent { 
                // node 'ZSstage1'
                label 'ZScustomer'
            }
            steps {
                echo "NODE_NAME = ${env.NODE_NAME}"
                sh 'hostname -i'
	       sh 'pwd'
            }
            post {
                always {
                    sh 'echo "Post Test on Linux ZSstage"'
                    sh 'echo "Check the Jenkins Page here http://ec2-54-86-91-68.compute-1.amazonaws.com:8080/jenkins"'
                }
            }
        }
    }
}
