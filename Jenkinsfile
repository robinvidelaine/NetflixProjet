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
                        }
                }

                stage('Run') { 
                         steps {
                                bat returnStdout: true, script: 'java -jar  target/netflix-1.0.0.jar  netflix_titles.csv'

                         }
                }
 stage('LoadWebPageIntoServer') { 
            steps {
                bat '''  
                    rmdir /s C:\xampp\htdocs\out\movies
                    del /s C:\xampp\htdocs\out\netflix.html
                    mkdir C:\xampp\htdocs\out\movies
                    move /y C:\ProgramData\Jenkins\.jenkins\workspace\NetflixProjet\out\*.html  C:\xampp\htdocs\out\movies
                '''
            }
        }
    }
}
