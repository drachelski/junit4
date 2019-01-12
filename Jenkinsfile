pipeline {
   agent any
   options {
       ansiColor('xterm')
   }
   stages {
       stage ('stage 1') {
           steps {
            git branch: 'mavenWrapper', changelog: false, poll: false, url: 'https://github.com/drachelski/junit4.git'
            echo 'first stage'
         }
       }
       stage ('stage 2') {
           steps {
           sh './mvnw clean install'
            echo 'second stage'
         }
       }
   }
   post {
       success {
           junit '**/target/surefire-reports/*.xml'
       }
   }
}