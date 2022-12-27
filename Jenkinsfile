pipeline {
  agent any
  stages {
    stage('Unit Test') { 
      steps {
        sh 'mvn clean test'
      }
    }
    stage('Deploy Exchange') { 
      steps {
        sh 'mvn clean deploy'
      }
    }
    stage('Deploy CH') { 
      steps {
        sh 'mvn clean deploy -DmuleDeploy -Dapplication.name=test-api -Denvironment=Sandbox -Dregion=us-east-1 -Dworkers=1 -DworkerType=MICRO -Dconn.app.client=47a593b9fe9c43f985dcefb931fcbf1e -Dconn.app.secret=0f29421b1dd2468A8f27329e35fB17de' 
      }
    }
  }
}