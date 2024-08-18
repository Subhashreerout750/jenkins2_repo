pipeline{
    agent any
    stages{
        stage
            ("Checkout Code Stages")
            {
            steps {
                git url:'https://github.com/Subhashreerout750/jenkins2_repo.git',branch:'main'
            }
        }
        stage("Cleanup Stage")
        {
            steps{
            sh 'docker rm -f $(docker ps -aq)'
            sh 'docker rmi -f myimage'
            }
        }
        stage
            ('build docker image')
            {
            steps{
                sh 'docker buid -t myimage .'
            }
        }
        stage('create container')
        {
            steps{
                sh 'docker run -d -p 8501:8501 myimage '
            }

        }

        }
    }
