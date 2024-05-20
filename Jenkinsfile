pipeline {
agent any
stages {
stage('Build') {
steps {
sh 'mvn -B -DskipTests clean package'
}
}
stage('K8s') {
steps {
sh 'kubectl set image deployment/teedy-deployment teedy-container=susjuny/teedy2024_manual'
}
}
}
}
