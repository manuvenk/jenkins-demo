pipeline{
agent {label 'docker'}
  stages{
    stage('REPLACE-CHANGES'){
      steps {
        sh '''
        sed -i  's/X/Y/g' index.html
        sed -i  's/ONE/FOUR/g' index.html
        sed -i 's/TWO/FIVE/g' index.html
        sed -i 's/THREE/SIX/g' index.html
        '''
            }
                     }
    stage('IMAGE-CREATION'){
      steps {
        sh '''
        docker rm -f WEBSERVER
        docker build . -t testrepo:ver1
        docker run --name WEBSERVER -p 8081:80 -d testrepo:ver1
        '''
            }                
        }

        }
       }
