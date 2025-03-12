pipeline {
    agent any
    environment {
        GIT_REPO = "https://github.com/yogesh/kubernetesmanifest.git"
    }
    stages {
        stage('Push to GitHub') {
            steps {
                withCredentials([string(credentialsId: 'github', variable: 'TOKEN')]) {
                    sh """
                        git config --global user.email "you@example.com"
                        git config --global user.name "Your Name"
                        git add .
                        git commit -m "Automated commit from Jenkins"
                        git push https://yogesh koli:$TOKEN@github.com/yogesh/kubernetesmanifest.git HEAD:master
                    """
                }
            }
        }
    }
}
