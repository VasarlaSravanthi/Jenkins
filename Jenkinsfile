pipeline {
    agent {
         node { 
            label 'roboshop' 
            }}
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')  
        } 
    environment{
        course = "Jenkins"
    }
    options { 
        disableConcurrentBuilds()
        timeout(time: 1, unit:"HOURS") 
    }
        //build 
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                        echo 'Building..'
                        echo "Course - ${course}"
                        sleep 6
                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.TOGGLE}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}"
                    """
                }
                
            }
        }
            stage('Test') {
            steps {
                script{
                    sh """
                        echo 'Testing..'
                    """
                }
               
            }
        }
        stage('Deploy') {
            steps {
                script{
                    sh """
                        echo 'Deploying....'
                    """
                }
                
            }
        }
    }
    // post build
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success { 
            echo "** Sucessfully Done **"
            echo "Completed ${course}"
        }
        failure { 
            echo 'I will run and check the error!'
        }
    }
}
