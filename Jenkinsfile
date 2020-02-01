pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'gradle build'
        bat 'gradle javadoc'
        archiveArtifacts 'build/libs/*.jar'
        archiveArtifacts 'build/docs/javadoc/*'
        archiveArtifacts 'build/test-results/test/*'
      }
    }

    stage('Mail Notification') {
      steps {
        echo 'reussi'
      }
    }

    stage('Code Analysis') {
      steps {
        withSonarQubeEnv 'sonarQube'
      }
    }

  }
}