pipeline {
    agent any
    environment {
        GIT_REPO = "https://github.com/yogesh/kubernetesmanifest.git"
    }
    stages {
        stage('Push to GitHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'github', usernameVariable: 'GIT_USER', passwordVariable: 'GIT_PASS')]) {
    sh "git push https://yogesh%20koli:****@github.com/tech-ai-manifest.git master"
}

    script {
        def safeGitUser = GIT_USER.replaceAll(' ', '%20') // Encode spaces in username if needed
        sh """
            git remote set-url origin https://${safeGitUser}:$GIT_PASS@github.com/yogesh-koli/tech-ai-manifest.git
            git config --global user.email "yogi@gmail.com"
            git config --global user.name " yogi"
            git checkout -b master || git checkout master
            git add .
            git commit -m "Automated commit from Jenkins" || echo "No changes to commit"
            git push --set-upstream https://github.com/yogesh-koli/tech-ai-manifest.git master
        """
    }
}

            }
        }
    }

