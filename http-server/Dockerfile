# DOCKER-VERSION        0.4.0
#
FROM   base:ubuntu-12.10
MAINTAINER  Thomas Frössman <thomasf@josysstem.se>
ADD sources.list /etc/apt/sources.list
RUN DEBIAN_FRONTEND=noninteractive apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes -q inotify-tools nginx-light && apt-get clean
ADD nginx-wrapper.sh /usr/sbin/nginx-wrapper
RUN chmod 775 /usr/sbin/nginx-wrapper
ADD pypi.nginx /etc/nginx/sites-available/default
RUN mkdir -p /srv/pypi && chmod a+rX /srv/pypi
# EXPOSE 80
# CMD ["/usr/sbin/nginx-wrapper"]

# end