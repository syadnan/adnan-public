// Scripted
// node {
//     stage("Build") {
//         echo 'Building...'
//     }

//     stage("Deploy") {
//         echo 'Deploying...'
//     }
// }


//Declarative
pipeline {
    agent any
    environment {
        dockerHome = tool 'myDocker'
        mavenHome = tool 'myMaven'
        PATH = "${dockerHome}/bin:${mavenHome}/bin:${env.PATH}"
    }

    stages {
        stage("Build") {
            steps {
                echo 'Building...'
                script {
                    docker.image('maven:3.6.3').inside {
                        sh 'mvn --version'
                    }
                }
                sh 'docker version'
            }
        }
        stage("Deploy") {
            steps {
                echo 'Deploying...'
            }
        }
    }
    post {
        success { echo "Pipeline finished successfully" }
        failure { echo "Pipeline failed" }
        always { echo "Pipeline finished" }
    }
}