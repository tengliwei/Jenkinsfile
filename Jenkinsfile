pipeline {
    agent any

    tools {
        maven 'local maven'  // 這個名稱要跟你在 Jenkins > Global Tool Configuration 裡設定的名字一致
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
