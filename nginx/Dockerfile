FROM nginx

# overwrite nginx configurations with our own
COPY conf/nginx.conf /etc/nginx/nginx.conf

# set up sites-available and sites-enabled directory structure
RUN mkdir /etc/nginx/sites-available /etc/nginx/sites-enabled
COPY conf/sites-available /etc/nginx/sites-available
RUN ln -s /etc/nginx/sites-available/default.conf /etc/nginx/sites-enabled/default.conf