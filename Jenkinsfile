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
        sh 'pwd'
        sh 'ls -la'
        writeFile file: 'build.txt', text: env.BUILD_ID
        def TOKEN = input(
            id: 'token', message: 'Digite seu token', parameters: [
                [$class: 'TextParameterDefinition', defaultValue: '', description: 'Token', name: 'token']
                ]
            )
        sh "git remote set-url origin https://boniestudo:${TOKEN}@github.com/bonifacio/jekins-test"
        sh 'git add .'
        sh "git commit -m ${env.BUILD_ID}"
        sh 'git push origin main'
    }
    stage('Finish!!!') {
        echo 'Finish!!!'
    }
}