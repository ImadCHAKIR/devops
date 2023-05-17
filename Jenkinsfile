pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                // Set up JDK and Maven paths
                env.JAVA_HOME = "${env.JAVA_HOME}"
                env.MAVEN_HOME = "${env.MAVEN_HOME}"
                env.PATH = "${env.MAVEN_HOME}/bin:${env.PATH}"

                // Run Maven compile command
                sh 'mvn compile'

                // Analyze the generated directory
                dir('devops/target') {
                    // Perform analysis on the generated directory
                    // Add your analysis steps here
                }
            }
        }

        stage('Test') {
            steps {
                // Run Maven test command
                sh 'mvn test'

                // Analyze the surefire-reports directory
                dir('nom_appli/target/surefire-reports') {
                    // Perform analysis on the generated surefire-reports directory
                    // Add your analysis steps here
                }
            }
        }

        stage('Package') {
            steps {
                // Run Maven package command
                sh 'mvn package'

                // Analyze the generated directory
                dir('nom_appli/target') {
                    // Perform analysis on the generated directory
                    // Add your analysis steps here
                }

                // Install the artifact in the local repository
                sh 'mvn install'

                // Analyze the local repository
                // Add your analysis steps here
            }
        }

        stage('Clean') {
            steps {
                // Run Maven clean command
                sh 'mvn clean'

                // Analyze the target directory
                dir('nom_appli/target') {
                    // Perform analysis on the target directory after clean
                    // Add your analysis steps here
                }
            }
        }

        stage('Clean Install') {
            steps {
                // Run Maven clean install command
                sh 'mvn clean install'

                // Analyze the build result
                // Add your analysis steps here
            }
        }

        stage('Site') {
            steps {
                // Run Maven site command
                sh 'mvn site'

                // Analyze the generated site directory
                dir('nom_appli/target/site') {
                    // Perform analysis on the generated site directory
                    // Add your analysis steps here
                }
            }
        }
    }
}
