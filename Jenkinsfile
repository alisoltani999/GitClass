pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'No tests defined.'
            }
        }
        stage('Deploy') {
            when {
                branch 'master'
            }
            steps {
                sh 'docker build -t nodejsapp .'
                sh 'docker run -d -p 3000:3000 nodejsapp'
            }
        }
    }
    post {
        failure {
            mail to: 'alicmspro@yahoo.com',
                 subject: 'Build Failed',
                 body: "Check Anisa project."
        }
    }
}
