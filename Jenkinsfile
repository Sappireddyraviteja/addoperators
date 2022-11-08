pipeline {

    agent any

    stages {
        
       //

//         stage('Code Checkout') {
//             steps {
//                 checkout([
//                     $class: 'GitSCM', 
//                     branches: [[name: '*/master']], 
//                     userRemoteConfigs: [[https://github.com/Sappireddyraviteja/addoperators.git]]
//                 ])
//             }
//         }

//         stage('SCM') {
//             steps{
//                 checkout scm
//             }
//   }

        stage('Build  Code') {
//             when {
//                 branch 'master'
//             }
            steps {
                sh 'g++ abc.cpp -o abc'
                sh './abc'

//                 sh 'echo Deploying'
//                 sh 'echo web-hook working'
            }
        }
   
      
//          stage(' Unit Testing') {
//             steps {
//                 sh 'echo Running Unit Tests'
               
//         }
 
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
    }
  }  
 post {
        always {
            echo "This block always runs."
        }
        changed {
            echo "This block runs when the current status is different than the previous one."
        }
        fixed {
            echo "This block runs when the current status is success and the previous one was failed or unstable."
        }
        regression {
            echo "This block runs when the current status is anything except success but the previous one was successful."
        }
        unstable {
            echo "This block runs if the current status is marked unstable."
        }
        aborted {
            echo "This block runs when the build process is aborted."
        }
        failure {
            echo "This block runs when the build is failed."
        }
        success {
            echo "This block runs when the build is succeeded."
        }
        unsuccessful {
            echo "This block runs when the current status is anything except success."
        }
        cleanup {
            echo "This block always runs after other conditions are evaluated."
        }
    }
