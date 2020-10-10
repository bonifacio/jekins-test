node {
    stage('Starting...') {
        checkout scm
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
        sh 'pwd'
        sh 'ls -la'
        writeFile file: 'build.txt', text: env.BUILD_ID
        def TOKEN = input(
            id: 'token', message: 'Digite seu token', parameters: [
                [$class: 'TextParameterDefinition', defaultValue: '', description: 'Token', name: 'token']
                ]
            )
        sh 'git config --global user.email "boni.estudo@gmail.com"'
        sh 'git config --global user.name "Boni Estudo"'
        sh "git remote set-url origin https://boniestudo:${TOKEN}@github.com/bonifacio/jekins-test.git"
        sh 'git checkout main'
        sh 'git add .'
        sh "git commit -m ${env.BUILD_ID}"
        sh 'git push'
    }
    stage('Finish!!!') {
        echo 'Finish!!!'
    }
}