FROM ruby

RUN	apt-get update -y && apt-get upgrade -y && apt-get install git libpq-dev build-essential nodejs yarn sqlite3 -y

ONBUILD EXPOSE 3000
ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# docker build -t ft-rails:on-build .
# docker run -it --rm -p 3000:3000 ex02.
