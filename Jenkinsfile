pipeline {
    agent any

    stages {
        stage ('Build and push backend and frontend images to ECR'){
            steps {
                sh '''
                cd ecr
                terraform destroy -auto-approve
                '''
            }
        }
    }
}
