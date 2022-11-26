node {
  stage('Apply Kubernetes files') {


     withCredentials([file(credentialsId: 'kube_config', variable: 'config_file')]) {
        writeFile file: 'config_file.yml', text: readFile(config_file)

         sh 'kubectl --kubeconfig=config_file.yml apply -f deploymet/'
         sh 'kubectl --kubeconfig=config_file.yml apply -f service/'
         sh 'kubectl --kubeconfig=config_file.yml apply -f ingress/'


        }
  }
}