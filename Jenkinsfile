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
    }
stage('DeployedServer') {
	parallel { 
	        stage('Customer Server1') {
            agent {
                //node 'ZSstage2'
                label 'ZScustomer'
            }
            steps {
                echo "NODE_NAME = ${env.NODE_NAME}"
				sh 'hostname -i'
                sh 'echo "Build Started"'
				sh 'pwd'
            }
            post {
                always {
                sh 'echo "Post Test on Unix ZSstage"'
                }
            }
        }
	        stage('Staging Server2') {
            agent {
                //node 'ZSstage2'
                label 'ZScustomer'
            }
            steps {
                echo "NODE_NAME = ${env.NODE_NAME}"
				sh 'hostname -i'
                sh 'echo "Build Started"'
				sh 'pwd'
            }
            post {
                always {
                sh 'echo "Post Test on Unix ZSstage"'
                }
            }
        }
	        stage('Staging Server3') {
            agent {
                //node 'ZSstage2'
                label 'ZScustomer'
            }
            steps {
                echo "NODE_NAME = ${env.NODE_NAME}"
				sh 'hostname -i'
                sh 'echo "Build Started"'
				sh 'pwd'
            }
            post {
                always {
                sh 'echo "Post Test on Unix ZSstage"'
                }
            }
        }
	        stage('Staging Server4') {
            agent {
                //node 'ZSstage2'
                label 'ZScustomer'
            }
            steps {
                echo "NODE_NAME = ${env.NODE_NAME}"
				sh 'hostname -i'
                sh 'echo "Build Started"'
				sh 'pwd'
            }
            post {
                always {
                sh 'echo "Post Test on Unix ZSstage"'
                }
            }
        }
	}
}
}
