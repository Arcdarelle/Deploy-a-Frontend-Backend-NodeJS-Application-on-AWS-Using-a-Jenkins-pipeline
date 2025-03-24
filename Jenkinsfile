pipeline {
    agent any

    stages {
        stage ('Build and push backend and frontend images to ECR'){
            steps {
                sh '''
                cd ecr 
                terraform state rm aws_lb_target_group.frontend_target_group
                terraform state rm aws_ecs_cluster.cluster
                terraform state rm aws_lb_target_group.backend_target_group
                terraform refresh
                terraform destroy -auto-approve
                '''
            }
        }

        stage ('Destroying the app to ECS'){
            steps{
                sh '''
                terraform refresh
                terraform destroy --auto-approve
                '''
            }
        }
    }
}
