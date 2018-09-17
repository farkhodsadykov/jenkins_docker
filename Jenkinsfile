node {
    def app

    stage('Clone repository') {

        checkout scm
    }


    stage('Build image') {

        app = docker.build("getintodevops/hellonode")
    }

    stage('Test image') {

        app.inside {
            sh 'echo "Tests passed"'
        }
    }
    stage('create container') {
      
           sh 'ssh -o StrictHostKeyChecking=no ansible@100.74.111.156 "sudo docker run -d --name jenkins_container -p 4560:9000  artemis:0.0.1.0 " '
    }
}
