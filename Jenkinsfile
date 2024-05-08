pipeline {
agent any
stages {
stage('Build') {
steps {
sh 'mvn -B -DskipTests clean package'
}
}
          stage('doc') {
            steps {
                sh 'mvn site --fail-never'
                sh 'mvn javadoc:jar --fail-never'
            }
        }
        stage('Test report') {
            steps {
                sh 'mvn test --fail-never'
                sh 'mvn surefire-report:report'
            }
        }
stage('pmd') {
steps {
sh 'mvn pmd:pmd'
}
}
}
post {
always {
archiveArtifacts artifacts: '**/target/site/**', fingerprint: true
archiveArtifacts artifacts: '**/target/**/*.jar', fingerprint: true
archiveArtifacts artifacts: '**/target/**/*.war', fingerprint: true
}
}
}
