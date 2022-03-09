pipeline {
    agent any
    tools{
        jdk 'jdk11'
        maven 'maven3'
         }
    
    stages {
        stage('Build') { 
            steps {
                bat 'mvn -B -DskipTests clean package'
                echo'build'
                }
            }
        stage('Run') { 
            steps {
                bat returnStdout: true, script: 'java -jar  target/netflix-1.0.0.jar  /netflix_titles.csv'
                echo'build'
                }
            }
        }
    }
