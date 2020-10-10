node {
    stage('Starting...') {
        echo 'Starting...'
    }
    stage('Building...') {
        echo 'Building...'
    }
    stage('Testing...') {
        echo 'Testing...'
    }
    stage('Deploying...') {
        echo 'Deploying...'
        writeFile file: 'build.txt', text: env.BUILD_ID
        sshagent(['c1f87d6d-d464-4053-a66d-e243ed20bc15']) {
            sh 'git add .'
            sh "git commit -m ${env.BUILD_ID}"
            sh 'git push origin main'
        }
    }
    stage('Finish!!!') {
        echo 'Finish!!!'
    }
}