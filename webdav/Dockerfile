FROM httpd:2.4
# Activer le module dav
RUN sed -i 's/#LoadModule dav_module/LoadModule dav_module/' /usr/local/apache2/conf/httpd.conf

# Activer le module dav_fs (ou tout autre module de stockage WebDAV que vous préférez)
RUN sed -i 's/#LoadModule dav_fs_module/LoadModule dav_fs_module/' /usr/local/apache2/conf/httpd.conf

# Activer le module auth_digest pour l'authentification WebDAV
RUN sed -i 's/#LoadModule auth_digest_module/LoadModule auth_digest_module/' /usr/local/apache2/conf/httpd.conf

# Créer un répertoire pour stocker les fichiers WebDAV
RUN mkdir /usr/local/apache2/webdav

# Configurer Apache pour le WebDAV
COPY ./apache2/webdav/webdav.conf /usr/local/apache2/conf/extra/webdav.conf
RUN echo 'Include conf/extra/webdav.conf' >> /usr/local/apache2/conf/httpd.conf

# Créer un répertoire pour stocker les fichiers .htpasswd
RUN mkdir /usr/local/apache2/htpasswd

# Copier le fichier .htpasswd pour l'authentification
COPY ./apache2/htpasswd/users.password /usr/local/apache2/htpasswd/users.password

# Exposer le port 80
EXPOSE 80

# Lancer Apache en mode avant-plan
CMD ["httpd-foreground"]