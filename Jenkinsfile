pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Kunal-Wagh282/LCEWEBFRONTEND'
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
        
        
        
        stage('Archive Artifacts') {
            steps {
                archiveArtifacts 'build/**'
            }
        }
        
        
    }
    
    post {
        success {
            mail to: 'kunalwagh282@gmail.com',
                subject: 'Build Successful',
                body: 'The build was successful. Ready for deployment!'
        }
        failure {
            mail to: 'kunalwagh82@gmail.com',
                subject: 'Build Failed',
                body: 'The build failed. Please investigate.'
        }
    }
}
