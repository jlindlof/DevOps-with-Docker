FROM ruby:2.6.0
WORKDIR /tmp
COPY rails-example-project .
RUN apt-get update && apt-get install -y nodejs
RUN gem install bundler
RUN bundle install
RUN rails db:migrate
CMD rails s
