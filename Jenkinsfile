pipeline {
    agent {
       node {
        label 'agent-1'
    }
}
environment { 
        greeting = "hello everyone"
    }
options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds() 
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh """
                echo 'hi'
                echo "$greeting"

                """
                
            }
        }
    }
post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure {
            echo 'i will alert you,when pipeline is failed'
        }
        success {
            echo 'i say hi it is success'
        }
    }
}