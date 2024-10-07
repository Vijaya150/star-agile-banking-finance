pipeline {
    agent any
    stages {
        stage('Checkout the code from GitHub') {
            steps {
                git url: 'https://github.com/Vijaya150/Banking-java-project1/'
                echo 'GitHub URL checked out successfully'
            }
        }
        stage('Publish HTML Report') {
            steps {
                // Specify the directory where index.html is located
                publishHTML([
                    allowMissing: false, 
                    alwaysLinkToLastBuild: false, 
                    keepAll: false, 
                    reportDir: 'reports',  // Update this path as needed
                    reportFiles: 'index.html', 
                    reportName: 'HTML Report', 
                    reportTitles: '', 
                    useWrapperFileDirectly: true
                ])
            }
        }
        stage('JUnit Test Results') {
            steps {
                junit testResults: '**/target/surefire-reports/*.xml', // Update this path as needed
                // Alternatively, specify the actual location of your JUnit XML files
                echo 'JUnit test results published'
            }
        }
    }
}

