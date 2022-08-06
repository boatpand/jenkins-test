// CODE_CHANGES = getGitChanges()
pipeline{
    agent any
    // define environment
    environment {
        NEW_VERSION = "1.3.0"
        // using credentials
        // SERVER_CREDENTIALS = credentials('')
    }
    stages{
        stage("build"){
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
            // condition
            when {
                expresstion {
                    BRANCH_NAME == 'master' || BRANCH_NAME == 'main'
                }
            }
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