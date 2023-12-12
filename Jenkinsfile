pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Usmankhaan/Project.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'Jenkins_server',
                            transfers: [sshTransfer(sourceFiles: '*/', remoteDirectory: '/myapp')],
                
                        )
                    ]
                )
            }
        }
    }
}
