#Version: 0.0.1

FROM ubuntu:14.04

MAINTAINER Ziming Zhang "zzmbpt@163.com"

ENV REFRESHED_AT 2015-09-03

RUN apt-get update
RUN apt-get install -y curl

#install nodejs and npm

RUN curl --silent --location https://deb.nodesource.com/setup_0.12 | sudo bash -
RUN apt-get install --yes nodejs

#install express
RUN mkdir -p /nodeWeb

#ADD https://github.com/Sebastian1011/myWeb.git /nodeWeb/myweb
WORKDIR /nodeWeb
RUN git clone https://github.com/Sebastian1011/myWeb.git -b master
WORKDIR /nodeWeb/myWeb
RUN npm install -g express-generator


RUN npm install

#install dependencies
RUN npm install express-react-views
RUN npm install react



EXPOSE 3000

CMD ["npm","start"]
