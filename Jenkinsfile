pipeline{

    agent any

    tools {
        maven 'maven'
        jdk 'Java'
    }
    
    stages {

        stage ('Compile Stage') {

            steps {

                    bat 'mvn clean install'

            }
        }
        stage ('Test Stage') {

            steps {

                    bat 'mvn test'

            }
        }


        stage ('Cucumber Reports') {

            steps {
                cucumber buildStatus: "UNSTABLE",
                    fileIncludePattern: "**/cucumber.json",
                    jsonReportDirectory: 'target'

            }

        }

    }

}
