pipeline {
    agent {
         node { 
            label 'roboshop' 
            }
        } 
    environment{
        course = "Jenkins"
    }
    options { 
        disableConcurrentBuilds() 
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