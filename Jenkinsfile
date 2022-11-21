pipeline {

    agent any

    stages {
        
       

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
                sh 'g++ abc.cpp'
                sh './a.out'

//                 bat 'echo Deploying'
//                 bat 'echo web-hook working'
            }
        }
   
      
//          stage(' Unit Testing') {
//             steps {
//                 sh 'echo Running Unit Tests'
               
//         }
 
  stage('SonarQube Analysis') {
      steps{
 //          scannerHome = tool 'Qube';
 //          withSonarQubeEnv() {
 //          sh '${scannerHome}/bin/sonar-scanner'}
          sh 'echo Running Code Analysis'
    }
    }
  }


//         stage('Code Analysis') {
//             steps {
//                 sh 'echo Running Code Analysis'
//             }
//         }

    
    post{
        //cleanWs(cleanWhenNotBuilt: false)
        always{
            mail to: "sapireddyteja@gmail.com",
            subject: "Test Email",
            body: " The wehook is working fine"
        }
    }
}
