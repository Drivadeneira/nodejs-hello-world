pipeline {
    agent any
    // tools (nodejs "nodejs")
    stages {
        // stage('Clone Repository'){
        //     steps {
        //         git branch: 'main', url: 'https://github.com/Drivadeneira/nodejs-hello-world.git'
        //     }
        // }
        stage('Install Dependencies') {
            steps {
                echo "Executing npm install ..."
                nodejs('Node-21.5.0') {
                    sh 'npm install'
                }
            }
        }

        stage('Perform API Testing') {
            steps {
                echo "Executing npm test ..."
                nodejs('Node-21.5.0') {
                    sh 'npm run test'
                }
            }
        }

        stage('Start Application') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "pankaj"
            }
            steps {
                nodejs('Node-21.5.0') {
                    sh 'npm start'
                }
            }
        }
    }
}
