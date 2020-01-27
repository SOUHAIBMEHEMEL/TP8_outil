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
        mail(from: 'Souhaib_Mehemel', subject: 'tp', body: 'tp 1111', to: 'fs_mehemel@esi.dz')
      }
    }

  }
}