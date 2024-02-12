pipeline{
    agent any

    tools {
         maven 'maven'
         jdk 'java'
    }

    stages{
        // clone code from git repository
        stage('checkout'){
            steps{
                checkout scm
                // checkout([$class: 'GitSCM', 
                // branches: [[name: '*/main']], 
                // extensions: [], 
                // userRemoteConfigs: [
                //         [
                //             credentialsId: 'github access', 
                //             url: 'https://github.com/upallapu/Jenkins_Automation.git'
                //         ]
                //     ]
                // ])
            }
        }
        stage('build'){
            // compile code using maven
            steps{
               sh 'mvn clean install -Dmaven.test.skip=true'
            }
        }
        // Stage to check code quality using sonarqube
        // stage('sonar'){
        //     steps{
        //        sh './sonar.sh'
        //     }
        // }
    }
}
