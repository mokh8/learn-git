pipeline{
    agent any

    parameters{
        string(name: 'username', description: '')
        string(name: 'last-name', description: '')
    }


    stages{

        stage("init"){
            steps{
                echo "hello ${params.username} ${params.last-name}"
            }
        }

        stage("build"){
            steps{
                echo "========Building========"
            }
        }

        stage("test"){
            steps{
                echo "========testing========"
            }
        }

        stage("deploy"){
            steps{
                echo "========deploying========"
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}