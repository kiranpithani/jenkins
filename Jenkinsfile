node('jdk11-mvn3.8.4') {
    stage('git') {
        git url: 'https://github.com/kiranpithani/jenkins.git', branch: "${params.BRANCH_TO_BUILD} 
    }
    stage('build') {
            sh '''
                echo "PATH=${PATH}"
                echo "M2_HOME=${M2_HOME}"
            '''
            sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
        }
    stage('archive'){
        archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }
}