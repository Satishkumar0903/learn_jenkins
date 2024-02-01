pipeline {
    agent {
    node {
        label 'Agent-1'   
    }
    }
    environment { 
        GREETING = 'HELLO JENKINS'
    }
    options {
        timeout(time: 1, unit: 'SECONDS') 
    }
//build
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
                    echo "Here i wrote shell script"
                    env
                    sleep 10
                """
            }
        }
    }

    //post
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'this is when pipe line is failed !'
        }
        success { 
            echo 'I will always say Hello when pipeline is success'
        }
    }
}