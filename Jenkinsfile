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
    stages {
        stage("Build") {
            steps {
                echo 'Building...'
            }
        }
        stage("Deploy") {
            steps {
                echo 'Deploying...'
            }
        }
    }
}