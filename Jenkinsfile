pipeline {
         agent any
         stages {
                 stage('Environment') {
                 steps {
                     echo 'Anuj BHATNAGAR'
                 }
                 }
                 stage('StagingServer') {
                 steps {
                    input('Do you want to proceed?')
                 }
                 }
                 stage('ProductionServer') {
                 when {
                       not {
                            branch "master"
                       }
                 }
                 steps {
                       echo "Hello"
                 }
                 }
                 stage('DeployedServer') {
                 parallel { 
                            stage('Unit Test') {
                           steps {
                                echo "Running the unit test..."
                           }
                           }
                            stage('Integration test') {
                              agent {
                                    docker {
                                            reuseNode true
                                            image 'ubuntu'
                                           }
                                    }
                              steps {
                                echo "Running the integration test..."
                              }
                           }
                           }
                           }
              }
}
