pipeline {
    agent any
    parameters {
        booleanParam(name:'Test-Jenkins', defaultValue: true, description:'this paramater help you to know project name')
        choice(name: 'namespace', choices:['Development','Testing','Production'], description: '' ) 
    }

    stages {
        stages {
            stage('check') {
                steps {
                    echo "checking your code"
                    echo "${params.namespace}"
                    echo "linting your code"
                    echo "running unit tests"
                }
            }

            stage('build') {
                steps {
                    echo "building your code"
                    echo "installing dependencies"
                    echo "configuring the environment"
                }
            }

            stage('test') {
                when {
                expression{
                    params.project == true 
                }
            }
                steps {
                    echo "testing your app" 
                }
            }
            
            stage('deployment') {  
                steps {
                    echo "deploying your code to staging environment"
                    echo "creating a release"
                    echo "sending notifications"
                }
            }    
        }
    }
}

