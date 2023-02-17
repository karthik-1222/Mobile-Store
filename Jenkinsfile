pipeline{
    agent any
    stages{
        stage ('checkout the code from SCM'){
            steps{
                echo 'checkout the code'
            }
        }
        stage ('Build the project'){
            steps{
                echo 'building the project'
                sh 'mvn clean install -DskipTests'
            }
        }
        stage('Sonarqube'){
            steps{
                echo 'Sonar Codequality'
                sh '''
                mvn clean verify sonar:sonar \
  -Dsonar.projectKey=mobile-store \
  -Dsonar.host.url=http://20.12.19.96:9000 \
  -Dsonar.login=sqp_1e9600913d563ebfdc7627ec102e28497d1556e3
  '''
            }
        }
    }
}