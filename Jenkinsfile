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
sh 'kubectl set image deployment/hello-node hello-node=susjuny/teedy2024_manual'
}
}
}
}
