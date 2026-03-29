pipeline {
    agent {
        label "Slave-2"
    }

    stages {

        stage('Deploy Q1') {
            steps {
                dir('Q1') {
                    git branch: 'Q1', url: 'https://github.com/ShreehariBandrawad/Dockerrepo2.git'
                    
                    sh '''
                    docker rm -f c1 || true
                    docker run -d --name c1 -p 8084:80 httpd
                    docker exec c1 rm -rf /usr/local/apache2/htdocs/*
                    docker cp . c1:/usr/local/apache2/htdocs/
                    docker exec c1 chmod -R 755 /usr/local/apache2/htdocs/
                    '''
                }
            }
        }

        stage('Deploy Q2') {
            steps {
                dir('Q2') {
                    git branch: 'Q2', url: 'https://github.com/ShreehariBandrawad/Dockerrepo2.git'
                    
                    sh '''
                    docker rm -f c2 || true
                    docker run -d --name c2 -p 8085:80 httpd
                    docker exec c2 rm -rf /usr/local/apache2/htdocs/*
                    docker cp . c2:/usr/local/apache2/htdocs/
                    docker exec c2 chmod -R 755 /usr/local/apache2/htdocs/
                    '''
                }
            }
        }

        stage('Deploy Q3') {
            steps {
                dir('Q3') {
                    git branch: 'Q3', url: 'https://github.com/ShreehariBandrawad/Dockerrepo2.git'
                    
                    sh '''
                    docker rm -f c3 || true
                    docker run -d --name c3 -p 8086:80 httpd
                    docker exec c3 rm -rf /usr/local/apache2/htdocs/*
                    docker cp . c3:/usr/local/apache2/htdocs/
                    docker exec c3 chmod -R 755 /usr/local/apache2/htdocs/
                    '''
                }
            }
        }
    }
}
