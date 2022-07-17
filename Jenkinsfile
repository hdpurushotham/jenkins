pipeline {
agent {
  label 'tomcat-slave'
}
stages {
  stage('Git Checkout') {
        parallel {
  stage('Git Checkout 1') {
    steps {
        git 'https://github.com/hdpurushotham/java_repo1.git'
    }
    }
  stage('Git Checkout 2') {
    steps {
        git branch: 'main', url: 'https://github.com/hdpurushotham/gs-maven.git'
    }
    }
		}
		}
  
  stage('Build stage') {
  parallel {
      stage('Build Stage 1') {
    steps {
        echo "This is Build Stage 1"
    }
    }
  stage('Build Stage 2') {
    steps {
        echo "This is Build Stage 2"
    }
    }
  }
}


  stage('Push Artifactory') {
    steps {
      sleep 15
    }
  }

  stage('Deploy') {
    steps {
      sh 'sudo cp /home/ec2-user/jenkins-slave1/workspace/test_for_tomcat/target/*.war /opt/tomcat/webapps/'
    }
  }

 }
}
