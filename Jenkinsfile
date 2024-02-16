pipeline {
     agent any
         stages {
             stage('Build') {
                 steps {
                     echo 'Application is in Building Phase'
                     bat 'mvn clean install'
                     }
                 }
             stage('Test') {
                 steps {
                     echo 'Application is in Testing Phase'
                     bat 'mvn test'
                       }
                 }
                 stage('Deploy to Cloudhub') { 
                   environment {
                                 ANYPOINT_CREDENTIALS = credentials('eyobtekle')
                               }
                   steps {
                            bat 'mvn clean deploy -DmuleDeploy -DmuleVersion=4.4.0 -Dusername=etekle25 -Dpassword=Asmara01 -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2'
                         }
                    }
         }
     }
