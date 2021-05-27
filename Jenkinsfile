pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
        jdk 'JDK11'
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git url: 'https://github.com/matthcol/movieapijava2021.git',
                    branch: 'dev'
					// Run Maven on a Unix Agent
					sh "mvn clean compile"
						// To run Maven on a Windows agent, use
						// bat "mvn -Dmaven.test.failure.ignore=true clean package"
					}
				}
 stage('Test') {
            steps {
                sh "mvn test"
			}
              
            }
stage ('package') {
steps { 
sh "mvn -DskipTests package"
}
         
            }
        }
    }
}