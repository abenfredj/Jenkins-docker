node {
    def app
    stage('clone') {
        checkout scm
    }
    stage('Build Image'){
        app = docker.build('anwarfredj/nginx')
    }
    stage('Run Image') {
        docker.image('anwarfredj/nginx').withRun('-p 8083:80') {
            c ->
            sh 'docker ps'
            sh 'curl localhost:8083'
        }
    }
}
