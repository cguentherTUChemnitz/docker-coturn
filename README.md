# docker-coturn
minimal alpine based coturn image

# usage
mount the volume /etc/coturn/ and place the turnserver.conf inside
The default command runns the coturn server pointing to the /etc/coturn/turnserver.conf config file.

lookup this reference https://github.com/coturn/coturn/blob/master/examples/etc/turnserver.conf to create your own turnserver.conf
