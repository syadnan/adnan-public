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
    agent {
        node {
            label 'docker_jenkins'
        }
    }
    // environment {
    //     dockerHome = tool 'myDocker'
    //     mavenHome = tool 'myMaven'
    //     PATH = "${dockerHome}/bin:${mavenHome}/bin:${env.PATH}"
    // }

    stages {
        stage("Build") {
            steps {
                echo 'Building inside Docker Agent container...'
                sh 'mvn --version'
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