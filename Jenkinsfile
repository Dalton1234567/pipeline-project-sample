pipeline{
    agent any
    stages{
        stage('One'){
            steps{
                echo "Welcome. This is Siddharth"
            }
        }
        
        stage('Two'){
            steps{
                input('do you want to proceed?')
            }
        }
        
        stage('Three'){
            when{
                not{
                    branch 'master'
                    
                }
                steps{
                    echo 'hello'
                }
            }
        }
        stage('Four'){
            parallel{
                stage('unit Test'){
                    steps{
                        echo 'Running test....'
                    }
                }
                stage('IntegrationTest'){
                    agent{
                        docker{
                            reuseNode false
                            image 'ubuntu'
                        }
                    }
                    steps{
                        echo 'running integration test'
                    }
                }
            }
        }
    }
}
