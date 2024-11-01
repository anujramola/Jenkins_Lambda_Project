pipeline {
    agent any
    environment {
        AWS_SAM_STACK_NAME = "jenkins-deploy"
        AWS_REGION = "us-east-1"
    }

    stages {
        stage('Setup') {
            steps {
                // Activate the virtual environment and install other dependencies
                sh """
                python3 -m venv venv
                . venv/bin/activate
                pip install -r lambda_deploy/tests/requirements.txt
                """
            }
        }

        stage('Test') {
            steps {
                // Activate the virtual environment and run tests using pytest
                sh """
                . venv/bin/activate
                pytest
                """
            }
        }

        stage('Build') {
            steps {
                // Activate the virtual environment and build the SAM application
                sh """
                . venv/bin/activate
                sam build -t lambda_deploy/template.yaml
                """
            }
        }

        stage('Deploy') {
            steps {
                // Activate the virtual environment and deploy the SAM application
                sh """
                . venv/bin/activate
                sam deploy -t lambda_deploy/template.yaml \
                    --no-confirm-changeset \
                    --no-fail-on-empty-changeset \
                    --stack-name jenkins-deploy \
                    --capabilities CAPABILITY_IAM
                """
            }
        }
    }
}
