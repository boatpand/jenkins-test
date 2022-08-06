// CODE_CHANGES = getGitChanges()
pipeline{
    agent any
    // define environment
    environment {
        NEW_VERSION = "1.3.0"
        // using credentials that create frum Jenkins UI with id
        SERVER_CREDENTIALS = credentials('server-credentials')
    }
    stages{
        stage("build"){
            // condition
            // when {
            //     expresstion {
            //         BRANCH_NAME == 'master' && CODE_CHANGES == true
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