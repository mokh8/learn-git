pipeline{
    agent any
    tools {
        maven '3.8.2'
    }
    stages{
       
        stage("test"){
            steps{
                echo "=========testingg========"
                sh 'mvn test'
            }
        }
        
        stage("build"){
            steps{
                echo "========Building========"
                sh 'mvn package'
                sh 'docker build -t mokh8/test-jenkins:2.0 .'
            }
        }

        stage("push"){
            environment{
                DOCKER = credentials('docker-hub')
            }
            steps{
                echo "========Pushing========"
                sh 'echo $DOCKER_PSW | docker login -u $DOCKER_USR --password-stdin'
                sh 'docker push mokh8/test-jenkins:2.0'
            }
        }
    }
    post{
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
