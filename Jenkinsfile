pipeline {
    agent any
    
    tools {nodejs "node"}

    stages {
        stage('Start') {
            steps {
                echo 'The build has started'
            }
        }
        stage('Clone the repository') {
            steps {
                git url: 'https://github.com/Brillianne/gallery.git', branch: 'master'
            }
        }
        stage('Install dependencies') {
            steps {
                sh '''
                   npm install
                   '''
            }
        }
       stage('Deploy to Render') {
            steps {
                sh '''
                   curl -X POST https://api.render.com/deploy/srv-cg7mrujhp8u9plii0k6g?key=xzaAdWrgyo4&ref=838c4bdc9cabb2a2d2802903021e8513015b9df5&ref=838c4bdc9cabb2a2d2802903021e8513015b9df5

                   '''
            }
        }
        stage('End') {
            steps {
                echo 'The build has ended'
            }
        }
    }
}