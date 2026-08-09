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
    agent { 
        dockerContainer { 
            image 'maven:3.6.3' 
        } 
    }

    stages {
        stage("Build") {
            steps {
                echo 'Building...'
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