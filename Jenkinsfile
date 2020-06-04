pipeline{

    agent {
        node {
            label 'master'
        }
    }

    stages{
        stage('maven-project - Build'){
            steps{
                // Maven build step
                withMaven(maven: 'localMaven'){
                    sh 'mvn clean package'
                    sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
                }
                
            }
        }
    }




}
