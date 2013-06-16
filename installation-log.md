# notes from installing


## installing bandersnatch

Inside a bash shell started like this: `docker run -i -t base bash` 

    apt-get update
    apt-get install python-pip
    run pip install -r https://bitbucket.org/ctheune/bandersnatch/raw/stable/requirements.txt
    run bandersnatch mirror


Commit as bandersnatch `docker commit XXXXXXXXXX bandersnatch`

Commence mirroring using a data volume  `docker run -v /srv/pypi/ bandersnatch bandersnatch mirror`


bandersnatch with the shared volume got the container id  `32a460b3d64f` which means that runnig docker like this will make it available:

    docker run -volumes-from 32a460b3d64f -i -t bandersnatch bash



## installing nginx

from inside `http-server`

    docker build .
    
    docker ps -l
    
    docker commit $(docker ps -l -q) pypi-http
    
    docker run -volumes-from 32a460b3d64f -p 80 -t pypi-http /usr/sbin/nginx-wrapper
    
    docker port $(docker ps -l -q) 80
