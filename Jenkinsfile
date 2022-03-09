pipeline {
    agent any
    tools{
        jdk 'jdk_8'
        maven 'maven3'
         }
    
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
                }
            
            }
        stage('Build') { 
            steps {
                sh returnStdout: true, script: 'java -jar  netflix-1.0.0.jar  ../netflix_titles.csv'
                echo'build'
                }
            }
        }
    }
