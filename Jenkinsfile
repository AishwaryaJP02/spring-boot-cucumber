pipeline{

    agent any
       environment {
	    PATH = "/opt/maven/apache-maven-3.8.2/bin:$PATH"
       }

    stages {

        stage ('Compile Stage') {
	
            steps {

               
                    sh 'mvn clean install'

                

            }
        }
    stage ('Test Stage') {
	
            steps {

                
                    sh 'mvn verify -Dunit-tests.skip=true'

                

            }
        }


        stage ('Cucumber Reports') {

            steps {
//                 cucumber buildStatus: "UNSTABLE",
//                     fileIncludePattern: "**/*.json",
//                     jsonReportDirectory: 'target'
		   cucumber buildStatus: null, fileIncludePattern: '**/*.json', jsonReportDirectory: 'target', sortingMethod: 'ALPHABETICAL'
            }
        }

            }

        }

    }

}
