pipeline {
    agent any

    // checks github every 2 min for new commits
    triggers {
        pollSCM('H/2 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo "Task: compile and package the code"
                echo "Tool: Maven"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Task: run unit tests to check the code works, then integration tests to check the parts work together"
                echo "Tools: JUnit for unit tests, Selenium for integration tests"
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Task: analyse the code to make sure it meets industry standards"
                echo "Tool: SonarQube"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Task: scan the code and dependencies for vulnerabilities"
                echo "Tool: OWASP Dependency-Check"
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Task: deploy the application to a staging server (AWS EC2 instance)"
                echo "Tool: AWS CLI"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Task: run integration tests on staging to check it works in a production-like environment"
                echo "Tool: Postman (Newman)"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Task: deploy the application to the production server (AWS EC2 instance)"
                echo "Tool: AWS CLI"
            }
        }
    }
}
