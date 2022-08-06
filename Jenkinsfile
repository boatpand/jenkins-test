pipeline{
    agent any

    parameters {
        // string(name: 'VERSION', defaultValue: '', description: 'version to deploy on prod')
        choice(name: 'VERSION', choices: ['1.1.0','1.2.0','1.3.0'])
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }

    // only 3 build tools available: gradle, maven, jdk
    // tools {
    //     maven 'Maven'
    // }

    // define environment
    // environment {
    //     NEW_VERSION = "1.3.0"
    //     // using credentials that create frum Jenkins UI with id
    //     SERVER_CREDENTIALS = credentials('server-credentials')
    // }

    stages{
        stage("build"){
            // condition
            // when {
            //     expresstion {
            //         params.executeTests
            //     }
            // }
            steps{
                echo "building the application"
                // use value of parameter in environment
                echo "building version ${NEW_VERSION}"
            }
            post{
                success{
                    echo "========building successfully========"
                }
                failure{
                    echo "========building failed========"
                }
            }
        }
        stage("test"){
            steps{
                echo "testing the application"
            }
            post{
                success{
                    echo "========testing successfully========"
                }
                failure{
                    echo "========testing failed========"
                }
            }
        }
        stage("deploy"){
            steps{
                echo "deploying the application"

                // Method credentials in environment{}
                // echo "deploying with ${SERVER_CREDENTIALS}"
                // sh "${SERVER_CREDENTIALS}"

                // Method withCredentials without environment{}
                // withCredentials([
                //     usernamePassword(credentials: 'server-credentials', usernameVariable: USER, passwordVariable: PWD)
                // ]) {
                //     script or command with USER, PWD parameter inside script
                //     sh "some script ${USER} ${PWD}"
                // }

                echo "deploying version ${params.VERSION}"
            }
            post{
                success{
                    echo "========deploying successfully========"
                }
                failure{
                    echo "========deploying failed========"
                }
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