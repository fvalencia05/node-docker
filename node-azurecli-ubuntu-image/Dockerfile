FROM ubuntu:latest

COPY package*.json ./

WORKDIR /usr/src/app

RUN apt-get -qqy update \
    && apt-get install -qqy software-properties-common \
    && add-apt-repository ppa:deadsnakes/ppa \
    && apt-get -qqy --no-install-recommends install \
    apt-transport-https \
    ca-certificates \
    wget \
    jq \
    curl \
    software-properties-common \
    python3.7 \
    build-essential \
    zlib1g-dev \
    libncurses5-dev \
    libgdbm-dev \
    libnss3-dev \
    libssl-dev \
    libreadline-dev \
    libffi-dev 

RUN curl -sL https://aka.ms/InstallAzureCLIDeb
RUN apt-get install -qqy azure-cli
RUN curl -sL https://deb.nodesource.com/setup_12.x
RUN apt-get install -qqy nodejs
RUN apt-get install -qqy npm
RUN npm install


COPY . .

EXPOSE  8080

CMD ["node", "serve.js"]