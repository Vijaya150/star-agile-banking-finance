pipeline {
    agent any
    stages {
        stage('Checkout the code from GitHub') {
            steps {
                git url: 'https://github.com/Vijaya150/Banking-java-project1/'
                echo 'GitHub URL checked out successfully'
            }
        }
        stage('Run Tests') {
            steps {
                // Run Maven tests
                sh 'mvn clean test' // This command will execute your tests
            }
        }
       stage('Publish HTML Report') {
            steps {
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
            }
       }
      stage('JUnit Test Results') {
            steps {
                // Specify the correct path to your JUnit XML report files
                junit testResults: 'target/surefire-reports/*.xml' // This is the correct path for your JUnit XML reports
                echo 'JUnit test results published'
            }
   }
    }
}
