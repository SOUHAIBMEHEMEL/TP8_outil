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
        emailext(subject: 'dddddddd', body: 'sssss', from: 'jenkins-notification@jenkins.com', to: 'fs_mehemel@esi.dz')
      }
    }

    stage('Code Analysis') {
      parallel {
        stage('Code Analysis') {
          steps {
            echo 'sonar not working'
          }
        }

        stage('Test Reporting') {
          steps {
            jacoco()
          }
        }

      }
    }

    stage('Deploiement') {
      steps {
        sh 'gradle publish'
      }
    }

  }
}