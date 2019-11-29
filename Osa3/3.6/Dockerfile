FROM ruby:2.6.0
RUN git clone https://github.com/docker-hy/rails-example-project /app && \
    cd /app && \
    bundle config --global frozen 1 && \
    gem install bundler && \
    bundle install && \
    chmod 777 /tmp && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    rails db:migrate && \
    apt-get purge -y --auto-remove curl && \
    rm -rf /var/lib/apt/lists/* && \
    useradd -m app && \
    chown -R app /app /tmp

WORKDIR /app
USER app
EXPOSE 3000
ENTRYPOINT rails s
