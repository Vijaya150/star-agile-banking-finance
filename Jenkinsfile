pipeline {
    agent any
    stages {
        stage('Checkout the code from GitHub') {
            steps {
                git url: 'https://github.com/Vijaya150/Banking-java-project1/'
                echo 'GitHub URL checked out successfully'
            }
        }
        stage('JUnit Test Results') {
            steps {
                // Ensure this path matches where your JUnit XML files are generated
                junit testResults: '**/target/surefire-reports/*.xml'  // Remove the comma after this line
                echo 'JUnit test results published'
            }
        }
    }
}

