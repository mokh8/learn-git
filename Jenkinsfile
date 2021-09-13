pipeline{
    agent any

    parameters{
        string(name: 'username', description: '')
        string(name: 'last_name', description: '')
    }


    stages{

        stage("init"){
            environment{
                my_cred = credentials('docker-hub')
            }
            steps{
                echo "hello $my_cred_USR - $my_cred_PSW"
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
            input {
                message "which env?"
                ok "done"
                parameters {
                    choice(name: 'ENV', choices: ['prod', 'dev', 'test'], description: '')
                }
            }
            steps{
                echo "========deploying to ${ENV}========"
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
