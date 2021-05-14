pipeline {
  agent any
  tools { 
        maven 'maven-3.8.1' 
        jdk 'jdk8' 
  }
  stages {
    stage ('Initialize path') {
            steps {
                bat '''
                    echo "----Printing System Path-----"
                    echo %path%
                    echo "----Printing Path Of maven------ "
                    echo %M2_HOME%
                ''' 
       }
    }
    stage('Install Parent Pom Dependencies On local Cache') {
      steps {
        echo "Install maven dependencies"
        bat 'mvn clean install'
      }
    }
  }
}
