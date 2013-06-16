# VERSION               0.0.2
# DOCKER-VERSION        0.4.0
#
from    base:ubuntu-12.10
maintainer  Thomas Frössman <thomasf@josysstem.se>
add sources.list /etc/apt/sources.list
run DEBIAN_FRONTEND=noninteractive apt-get update
run DEBIAN_FRONTEND=noninteractive apt-get install -y -q nginx-light && apt-get clean
add nginx-wrapper /usr/sbin/nginx-wrapper
add bandersnatch.nginx /etc/nginx/sites-enabled/default
expose 80
cmd ["/usr/sbin/nginx-wrapper"]
