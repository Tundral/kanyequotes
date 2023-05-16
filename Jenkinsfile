

pipeline {
    agent {
            node {
                label 'docker-agent-python'
            }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}

