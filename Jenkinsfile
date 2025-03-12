pipeline {
    agent any
    environment {
        GIT_REPO = "https://github.com/yogesh/kubernetesmanifest.git"
    }
    stages {
        stage('Push to GitHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'github', usernameVariable: 'GIT_USER', passwordVariable: 'GIT_PASS')]) {
                    sh """
                        sh 'git remote set-url origin https://$GIT_USER:$GIT_PASS@github.com/your-username/your-repo.git'
                        git config --global user.email "you@example.com"
                        git config --global user.name "Your Name"
                        git add .
                        git commit -m "Automated commit from Jenkins"
                        git push origin master
                       
                        
                    """
                }
            }
        }
    
}
