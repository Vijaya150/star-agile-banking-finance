pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Vijaya150/Banking-java-project1/'
                 echo 'github url checkout'
            }
        }
       stage('Publish HTML Report') {
            steps {
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
            }
       }
    stage('JUnit Test Results') {
            steps {
                junit testResults: '**/target/surefire-reports/*.xml' // Ensure this matches where your reports are generated
                echo 'JUnit test results published'
            }
   }
    }
}
