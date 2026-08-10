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
    // agent any
    agent {
        node {
            // label 'docker_jenkins'
            label 'docker alpine'
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
                sh 'echo Hello Mtotootot'
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