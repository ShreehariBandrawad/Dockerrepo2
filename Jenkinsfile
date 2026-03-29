pipeline{
	agent any
	   stages{
		    stage('Deploy Q1-Branch'){
		       steps{
			    git branch: 'Q1', url: 'https://github.com/ShreehariBandrawad/Dockerrepo2.git'
			    script{
				sh '''
				docker rm -f c1 || true
				docker run -d --name c1 -p 80:80 httpd
				docker exec c1 rm -rf /usr/local/apache2/htdocs/*
				docker cp . c1:/usr/local/apache2/htdocs/
				docker exec c1 chmod -R 755 /usr/local/apache2/htdocs/
				'''
			    }

			}	
		    }
	            stage('Deploy Q2-Branch'){
                       steps{
                            git branch: 'Q2-Branch', url: 'https://github.com/ShreehariBandrawad/Dockerrepo2.git'
                            script{
                                sh '''
                                docker rm -f c2 || true
                                docker run -d --name c2 -p 90:80 httpd
                                docker exec c2 rm -rf /usr/local/apache2/htdocs/*
                                docker cp . c2:/usr/local/apache2/htdocs/
								                docker exec c2 chmod -R 755 /usr/local/apache2/htdocs/
                                '''
                            }

                        }
                    }
	             stage('Deploy Q3-Branch'){
                       steps{
                            git branch: 'Q3-Branch', url: 'https://github.com/ShreehariBandrawad/Dockerrepo2.git'
                            script{
                                sh '''
                                docker rm -f c3 || true
                                docker run -d --name c3 -p 8080:80 httpd
                                docker exec c3 rm -rf /usr/local/apache2/htdocs/*
                                docker cp . c3:/usr/local/apache2/htdocs/
								                docker exec c3 chmod -R 755 /usr/local/apache2/htdocs/
                                '''
                            }

                        }
                    }
	}
}
