pipeline{
    agent any

    parameters{
        string(name: 'username', description: '')
        string(name: 'last_name', description: '')
    }


    stages{

        stage("init"){
            steps{
                echo "hello ${params.username} - ${params.last_name}"
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
            input{
                message: "which env?"
                ok: "done"
                parameters{
                    choice(name: 'env', choices['prod', 'dev', 'test'], description: '')
                }
            }
            steps{
                echo "========deploying to ${params.env}========"
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
