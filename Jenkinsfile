pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                // Run Maven compile command
                sh 'mvn compile'

                // Analyze the generated directory
//                 dir('devops/target') {
//                     // Perform analysis on the generated directory
//                     // Add your analysis steps here
//                 }
            }
        }

        stage('Test') {
            steps {
                // Run Maven test command
                sh 'mvn test'

                // Analyze the surefire-reports directory
//                 dir('devops/target/surefire-reports') {
//                     // Perform analysis on the generated surefire-reports directory
//                     // Add your analysis steps here
//                 }
            }
        }

        stage('Package') {
            steps {
                echo 'Package'
                // Run Maven package command
                sh 'mvn package'

                // Analyze the generated directory
//                 dir('devops/target') {
//                     // Perform analysis on the generated directory
//                     // Add your analysis steps here
//                 }

                // Install the artifact in the local repository
                sh 'mvn install'
            }
        }

        stage('Clean') {
            steps {
                echo 'Clean'
                // Run Maven clean command
                sh 'mvn clean'

                // Analyze the target directory
//                 dir('devops/target') {
//                     // Perform analysis on the target directory after clean
//                     // Add your analysis steps here
//                 }
            }
        }

        stage('Clean Install') {
            steps {
                echo 'clean install'
                // Run Maven clean install command
                sh 'mvn clean install'

                // Analyze the build result
                // Add your analysis steps here
            }
        }

        stage('Site') {
            steps {
                echo 'site'
                // Run Maven site command
                sh 'mvn site'

                // Analyze the generated site directory
//                 dir('devops/target/site') {
//                     // Perform analysis on the generated site directory
//                     // Add your analysis steps here
//                 }
            }
        }
    }
}
