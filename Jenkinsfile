pipeline {
    agent any
    tools{
        jdk 'jdk_8'
        maven 'maven3'
         }
    
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package'
                echo'build'
                }
            }
        stage('Run') { 
            steps {
                sh returnStdout: true, script: 'java -jar  netflix-1.0.0.jar  ../netflix_titles.csv'
                echo'build'
                }
            }
        }
    }
