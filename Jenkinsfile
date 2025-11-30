pipeline {
    agent any

    stages {
        stage('Timed Step') {
            steps {
                script {
                    def start = System.currentTimeMillis()

                    // Your actual build steps
                    echo 'Running build step...'
                    sleep(time: 5, unit: 'SECONDS') // Simulate a time-consuming task

                    def end = System.currentTimeMillis()
                    def duration = (end - start) / 1000
                    echo "Step took ${duration} seconds."
                }
            }
        }
        stage('date step') {
            steps {
                script {
                    def currentDate = new Date().format("dd-MM-yyyy HH:mm:ss", TimeZone.getTimeZone('UTC'))
                    echo "Current Date (UTC): ${currentDate}"
                }
            }
        }
        stage('output') {
            steps {
                echo 'This is printed in the Console Output'
                sh 'echo "Hello from shell"'
            }
        }
        stage('\n meaning') {
            steps {
                echo 'one\ntwo\nthree\nfour\nfive'
            }
        }
        stage('\t meaning') {
            steps {
                echo 'one\ttwo\tthree\tfour\tfive'
            }
        }
    }stage ("auto deploy") {
            steps {
                withKubeConfig(credentialsId: 'kubeconfig-dev-kt-k8s') {
                script {
                    sh "kubectl apply -f https://raw.githubusercontent.com/rancher/local-path-provisioner/master/deploy/local-path-storage.yaml"
                 
                    
                }
                }
            }
        }
}
    

        
    

