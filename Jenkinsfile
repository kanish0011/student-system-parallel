pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com<your-username>/student-system-parallel.git'
            }
        }
        stage('Parallel Data Checks') {
            parallel {
                stage('Attendance Verification') {
                    steps {
                        bat 'python check_attendance.py'
                    }
                }
                stage('Marks Verification') {
                    steps {
                        bat 'python check_marks.py'
                    }
                }
            }
        }
    }
}
