FROM ruby:latest

RUN apt-get update && \
    apt-get install -y build-essential
RUN curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
    apt-get update && apt-get install -y yarn
RUN curl -sL https://deb.nodesource.com/setup_13.x | bash - && \
    apt-get install -y nodejs

RUN mkdir /app
WORKDIR /app

ADD ./Gemfile Gemfile
ADD ./Gemfile.lock Gemfile.lock

RUN bundle install
RUN bundle exec rails webpacker:install

ADD . /app
RUN yarn install

EXPOSE 3030

CMD ["bundle", "exec", "rails", "s", "-b", "0"]
