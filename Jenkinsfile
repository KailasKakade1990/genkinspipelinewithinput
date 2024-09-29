pipeline {
agent any
 stages {
  stage('Create build output') {
   steps {
    script {
     // Make the output directory.
     sh "mkdir -p output"
     // Write a useful file, which is needed to be archived.
     writeFile file: "output/usefulfile.txt", text: "This file is useful, need to archive it."
    // Write a useless file, which is not needed to be archived.
     writeFile file: "output/uselessfile.md", text: "This file is useless, no need to archive it."
     }
    }
   }
   stage('Archive build output') {
    steps {
    // Archive the build output artifacts.
     archiveArtifacts artifacts: 'output/*.txt', excludes: 'output/*.md'
     }
   }
// input message
     
        stage('input the message') {
            steps {
                // Requesting user input
                script {
                    def userInput = input(message: 'Please provide a message:', parameters: [string(defaultValue: 'kailas', description: 'Enter your message', name: 'MESSAGE')])
                    echo "User input is: ${userInput}"
                }
            }
  }
}
