FROM ruby:3.0.2

COPY . .

RUN bundle install

RUN gem install rails

EXPOSE 3000

CMD bin/rails server -b 0.0.0.0
