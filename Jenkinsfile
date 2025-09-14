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
    }
}
    

        
    

