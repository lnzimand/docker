FROM ruby

LABEL maintainer="YaQwaQwa <lnzimand@student.wethinkcode.co.za>"

RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# How to build it?
# docker build -t <tag name> .

git clone https://github.com/docker/docker.git