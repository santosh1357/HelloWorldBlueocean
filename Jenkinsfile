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
                    echo $PWD
                    '''
            }    
        }
        stage('Upload to AWS') {
            steps{
                withAWS(region:'ap-south-1', credentials:'ci-cd-blueocean-aws'){
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'mybucket-for-testing/ci-cd')
                }
            }
        }
    }
}