pipeline{
    agent any
    stages{
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