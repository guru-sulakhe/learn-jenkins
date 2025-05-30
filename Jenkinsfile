pipeline {
    agent {
        label 'AGENT-1' //Runs the jenkinsfile in the AGENT-1 node(instance)
    }
    options {
        timeout(time: 30, unit: 'MINUTES') //Runs the pipeline for 30 minutes, if it takes more time then pipeline will be failed
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment{
        DEPLOY_TO ='production'
        GREETING ='good morning' 
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo this is buld'
                sh 'env'
            }
        }
        stage('Test') {
            steps {
                sh 'echo this is test'
                sh 'sleep 10'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo this is deploy'
            }
        }
        stage('Print Parameters'){
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
                echo "this is github webhook"
            }
        }

    }
        post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success { 
            echo 'I will run only when pipeline is success'
        }
        failure { 
            echo 'I will run only when pipeline is failure'
        }
      }
}