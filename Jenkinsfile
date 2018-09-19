node {
    dir("/root/"){
    checkout scm

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("ethilesen/falskeapp")
    }

    input 'Do you want to proceed with Deployment?'
    stage "Deploy"

        sh "kubectl set image deployment/flasekeapp"
        sh "kubectl rollout status deployment/flasekeapp"
}
}
}

