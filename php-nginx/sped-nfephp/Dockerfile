FROM felipefinhane/php-nginx:latest

# Install php extensions                                                                                   
RUN apk --no-cache add \
        php7-mbstring \                                                                                                 
        php7-dom \                                                                                                      
        php7-soap \                                                                                                     
        php7-simplexml \                                                                                                
        php7-gd \                                                                                                       
        php7-mcrypt \                                                                                                   
        php7-zip \                                                                                                      
        php7-common   

#COMPOSER INSTALL                                                                                                       
RUN echo "---> Installing Composer" && \
        curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \       
        echo "---> Cleaning up" && \                                                                                    
        rm -rf /tmp/*    

