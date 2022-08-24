FROM ubuntu:focal
COPY requirements.txt .
RUN apt-get update && \
    apt-get install -y python3.8 
RUN apt-get install -y pip    
RUN pip install -r requirements.txt

#user add
ARG UNAME=dev
ARG UID=1000
ARG GID=1000
RUN groupadd -g $GID -o $UNAME
RUN useradd -m -u $UID -g $GID -o -s /bin/bash $UNAME
USER $UNAME

CMD /bin/bash
#build using docker build --build-arg UID=$(id -u) --build-arg GID=$(id -g) -t image:tag .