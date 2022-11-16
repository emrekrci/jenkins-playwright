pipeline {
    agent any
    stages{
        stage('Clone Project Repository'){
            steps{
                script{
                    git url: 'https://github.com/emrekrci/jenkins-playwright.git'
                }
            }
            
    }
    stage('Build Project'){
        steps{
            bat "npm install"
        }
        
    }
    stage('Run Project'){
        steps{
            catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                bat "c:\\Users\\Emre\\Desktop\\runCommand.bat"
            }
            
        }
       
    }
    stage('Report'){
        steps{
            junit "*.xml"
        }
    }
}
}