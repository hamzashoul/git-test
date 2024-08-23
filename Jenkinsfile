pipeline {
    agent any

    stages {
        stage('one') {
            steps {
                echo "Hello, it's Hamza from edureka learning course"
            }
        }
        stage('two') {
            steps {
                input('Do you want to proceed?')
            }
        }
        stage('three') {
            when {
                not {
                    branch 'master'
                }
            }
            steps {
                echo "Hello"
            }
        }
        stage('four') {
            parallel {
                stage('Unit Test') {
                    steps {
                        echo "Running unit test.."
                    }
                }
                stage('Integration Test') {
                    agent {
                        docker {
                            image 'ubuntu'
                            reuseNode false
                        }
                    }
                    steps {
                        echo "Running integration test.."
                    }
                }
            }
        }
    }
}
