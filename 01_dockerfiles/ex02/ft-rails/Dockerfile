FROM ruby
RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN gem install bundler:1.10.4
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# How to build it?
# docker build -t <tag name> .