pipeline{

    agent any

    stages{
        
        stage('Paso 1: Probando funcionamiento'){
            steps{
                script{
                    echo "Paso 1 del Jenkisfile"
                }
            }
        }

        stage('Paso 2: Build'){
            steps{
                script{
                    sh '''
                        docker build -t python-ml:v0.1 .
                    '''
                }
            }
        }

        stage('Paso 3: Run'){
            steps{
                script{
                    sh '''
                        docker run -dt --name python-ml-0.1 python-ml:v0.1
                    '''
                }
            }
        }


    }

    post{
        
        always{
            sh "echo 'Ha finalizado el Pipeline de Jenkins'"
        }
        success{
            sh "echo 'Con exito!'"
        }
        failure{
            sh "echo 'Con error!'"
        }

    }

}