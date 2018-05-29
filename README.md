# docker-coturn
minimal alpine based coturn image

# usage
mount the volume /etc/coturn/ and place the turnserver.conf inside
The default command runns the coturn server pointing to the /etc/coturn/turnserver.conf config file.

lookup this reference https://github.com/coturn/coturn/blob/master/examples/etc/turnserver.conf to create your own turnserver.conf

# certificates
self signed certs can be generated with by running the following stuff inside the container:

    docker exec -it <yourRunningCoturnInstance> /bin/sh
    cd /etc/coturn
    openssl req -x509 -newkey rsa:2048 -keyout turn_server_pkey.pem -out turn_server_cert.pem -days 3001 -nodes

those certs can be provided in the config file via their relative path to the config file, e.g.:

    cert=./turn_server_cert.pem
    pkey=./turn_server_pkey.pem
