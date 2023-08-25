pipeline{
    agent{label 'built-in'}
    tools{maven 'M3-training'}
    stages{
        stage('checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/jmanuel-dev/training-jenkins-springPetClinic.git'
            }
        }
        stage('compile'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('deploy'){
            steps{
                sh 'java -jar /var/jenkins_home/workspace/petClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
