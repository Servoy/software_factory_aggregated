pipeline {
  agent any
  
  triggers { pollSCM('H/3 * * * *') }
  
  stages {
    stage('SCM') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'software_factory_build_scripts']], submoduleCfg: [], userRemoteConfigs: [[url: 'e:/GitHome/git/software_factory_build_scripts']]])
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'software_factory_build_tools']], submoduleCfg: [], userRemoteConfigs: [[url: 'e:/GitHome/git/software_factory_build_tools']]])
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'software_factory_sample_solutions']], submoduleCfg: [], userRemoteConfigs: [[url: 'e:/GitHome/git/software_factory_sample_solutions']]])
      }
    }

    stage('Run ant build') {
      steps {
        echo 'DONE.'
      }
    }

  }
}