

pipeline {
    agent {
            node {
                label 'maven'
            }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
            
        }
        stage('Publish') {
            steps {
            nexusPublisher nexusInstanceId: 'A', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'war/target/jenkins.war']], mavenCoordinate: [artifactId: 'kanyequotes', groupId: 'com.dymesolutions.lauri', packaging: 'jar', version: '2.23']]]
            }
        }
    }
}

