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
sh 'kubectl set image deployment/hello-node teedy2024-manual-977zh=susjuny/teedy2024_manual'
sh 'minikube service hello-node'
}
}
}
}
