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
                python3 -m venv ./my-venv
                chmod +x ./my-venv/bin/activate
                
                echo "Wap81802" | chown -R root:root ./my-venv
                echo "Wap81802" | chmod -R 755 ./my-venv
                
                echo "Wap81802" | ./my-venv/bin/activate
                echo "Wap81802" | pip3 install -r requirements.txt
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
