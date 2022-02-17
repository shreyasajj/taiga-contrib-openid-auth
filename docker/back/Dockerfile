ARG TAIGA_VERSION=latest
ARG RELEASE=master
FROM taigaio/taiga-back:${TAIGA_VERSION}
RUN apt-get update && apt-get install git -y

WORKDIR /app

COPY . /app

RUN cd taiga-contrib-openid-auth/back; pip install -e .
COPY config.py taiga-back/settings/config.py
ENV OPENID_SCOPE="openid email"
