pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Vijaya150/star-agile-banking-finance'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with vijaya'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with vijaya'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with vijaya'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with vijaya'){
            steps{
                sh 'mvn package'
            }
        }
       stage('Generate Test Report') {
      steps {
        echo 'This stage generate Test report using TestNG'
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/banking01/target/surefire-reports', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
                          }
            }
}
}
