pipeline{
    agent{
        label "Jenkins-Agent"
    }
    tools{
        jdk 'java17'
        maven 'Maven3'
    }
    stages{
        stage("Cleanup Workspace"){
            steps{
                cleanWs()
            }
        }
        stage('Checkout from SCM'){
            steps{
                git branch: 'main' , credentials: 'github', url:'https://github.com/i-amit88/Jenkins-deploy-to-eks-cluster'

            }
        }
        stage("Build Application"){
            steps{
                sh "mvn clean package"
            }
        }
        stage{
            steps{
                sh "mvn test"
            }
        }
    }
    
}