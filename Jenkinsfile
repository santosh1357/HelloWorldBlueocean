pipeline {
    agent any
    stages{
        stage('Lint Html'){
            steps {
                sh 'tidy -q -e *.html'
            }
        }        
        stage('Build') {
            steps {
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                    '''
            }    
        }
    }
}