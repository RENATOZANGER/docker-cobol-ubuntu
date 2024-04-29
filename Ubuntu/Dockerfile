FROM ubuntu:latest

# update and install packages
RUN apt-get update && apt-get install -y \
    #g++ make libpq-dev libpq5 postgresql-server-dev-all \
    gnucobol \
    gcc \
    apt-utils \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

COPY *.cbl /
RUN cobc -x -free -o /hello /hello.cbl && \
    cobc -x -free -o /hello2 /hello2.cbl

#exec hello.cbl
CMD ["/hello"]

#exec hello2.cbl
#CMD ["/hello2"]

# docker build -t cobol .
# docker run --rm cobol
