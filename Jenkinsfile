pipeline {

    agent {label 'jenkins-slave'}

    stages {

        stage('build') {

            steps {

                sh 'whoami'

                sh 'pwd'

                sh 'pkill java'

                sh 'echo ${BUILD_NUMBER}'                
               
               sh 'ls -la'
    
               sh  'touch test.txt'

               sh 'scp test.txt jenkins-master.personal:~'
                
                sh 'sleep 20s'
                
                sh ' sed -i s/{BuildNumber}/${BUILD_NUMBER}/g testScript.sh'
                
                sh ' sed -i s/{Token}/test123/g testScript.sh '
                
                sh 'sh testScript.sh | ssh jenkins-master.personal /bin/bash'
                
            }

    }

}

}
