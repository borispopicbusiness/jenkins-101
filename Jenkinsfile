pipeline {
    agent { 
        node {
            label 'cloud-python3-label'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building..."
                sh '''
                cd myapp
                echo "Wap81802" | python3 -m venv ./my-venv
                echo "Wap81802" | chmod +x ./my-venv/bin/activate
                
                echo "Wap81802" | source ./my-venv/bin/activate
                echo "Wap81802" | pip3 install fire
                #echo "Wap81802" | pip3 install --upgrade pip setuptools wheel
                #echo "Wap81802" | pip3 install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing..."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Brad
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver...'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
