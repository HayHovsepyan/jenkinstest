node {
    def app

    stage('Clone repository') {
        checkout scm
    }

    stage('Build imageee') {
        app = docker.build("hayhovsepyan/jenkinstest")
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
