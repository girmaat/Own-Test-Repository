pipeline {
    agent any
    //triggers {cron('* * * * *')}
    options { timeout (time : 5)}
    parameters{
        booleanParam( name: 'DEBUG_BUILD', defaultValue: true, description : 'Is it the debuing build?')
    }

    stages {
        stage('Build') {
            environment { NAME = "Girma"}
            when {expression {return params.DEBUG_BUILD}}
            steps {
                echo "Building step from $NAME"
                script {
                    def browsers =['chrome', 'fireforx']
                    for (int i =0; i < browsers.size(); ++i){
                        echo "Testing the ${browsers[i]} brwser."
                    }
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }

    }
    post{
        always{
            echo 'I will always say Hello again!'
        }
    }
}