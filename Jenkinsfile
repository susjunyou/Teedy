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
sh 'kubectl set image susjuny/teedy2024_manual container-name=079a60703b5acc700d64e7c2534e5b36791f0ae8a7f669a23b0918377a3fc0d4'
}
}
}
}
