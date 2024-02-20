pipeline {
    agent {
       node {
        label 'AGENT-1'
    }
}
environment { 
        greeting = "hello everyone"
    }
options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds() 
    }
parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                echo 'namas'
                echo "$greeting"

                """
                
            }
        }
        stage('check params') {
            steps {
                sh """
                echo  "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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