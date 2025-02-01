pipeline {
    agent any

    stages {

        stage('CODE QUALITY'){

            steps {
                echo "SONAR ANALYSIS"
                sudo docker run  --rm -e SONAR_HOST_URL="http://23.22.143.56:9000" -e SONAR_LOGIN="sqp_f5123cc25e50c9a0725daa92102f8e2cac3e7476"  -v ".:/usr/src" sonarsource/sonar-scanner-cli:5.0 -Dsonar.projectKey=lms-frontend
            }
        }

        stage('Building a docker image') {

            steps{
                echo "Build of application"
                docker build -t sankimanki/lms-job .
            }
        }

    }
}