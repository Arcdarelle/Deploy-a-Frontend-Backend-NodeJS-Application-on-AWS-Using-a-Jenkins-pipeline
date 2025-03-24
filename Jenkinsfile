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

        stage ('Destroying the app to ECS'){
            steps{
                sh 'terraform destroy --auto-approve'
            }
        }
    }
}
