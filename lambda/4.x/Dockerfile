From ubuntu:16.04                                                                                                                    
MAINTAINER Jimmy Yang <gankkank@gmail.com>                                                                                           
                                                                                                                                     
RUN apt-get update && \                                                                                                              
  apt-get install -y python-pip curl                                                                                                 
                                                                                                                                     
# Install Nodejs 4.x                                                                                                                 
RUN curl -sL https://deb.nodesource.com/setup_4.x | bash -                                                                           
                                                                                                                                     
RUN apt-get install -y nodejs                                                                                                        
                                                                                                                                     
RUN pip install awscli                                                                                                               
                                                                                                                                     
# Install Libraries                                                                                                                  
RUN npm install -g yarn                                                                                                              
# claudia@2.1.0 serverless@1.0.3 typescript@2.0.3                                                                  
RUN yarn global add claudia@2.1.0 serverless@1.0.3 typescript@2.0.3
