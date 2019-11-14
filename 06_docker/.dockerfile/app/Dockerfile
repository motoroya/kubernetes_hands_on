FROM ruby:2.6.5

RUN apt-get update -qq && \
    apt-get install -y build-essential

RUN mkdir /app
WORKDIR /app

ADD Gemfile /app/Gemfile
ADD Gemfile.lock /app/Gemfile.lock
