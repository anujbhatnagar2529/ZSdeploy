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
    			sh './buildcreateApacheTomcat.sh'
    			sh 'pwd'
    			sh './buildcreateJenkins.sh'
                sh 'echo "Build Finished"'
				sh 'pwd'
    			sh './sshpassInstall.sh'				
            }
        }
        stage('Staging Server1') {
            agent { 
                node 'ZSstage1'
                // label 'ZSstage'
            }
            steps {
				echo "NODE_NAME = ${env.NODE_NAME}"
				sh 'hostname -i'
				sh 'pwd'
                sh './deployApacheTomcat.sh'
                sh 'echo "Apache Tomcat Deployed"'
				sh 'pwd'
                sh './deployJenkins.sh'
                sh 'echo "Jenkins Application Deployed"'
            }
            post {
                always {
                    sh 'echo "Post Test on Linux ZSstage"'
                    sh 'echo "Check the Jenkins Page here http://ec2-54-86-91-68.compute-1.amazonaws.com:8080/jenkins"'
                }
            }
        }
        stage('Staging Server2') {
            agent {
                node 'ZSstage2'
                //label 'ZSstage'
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
