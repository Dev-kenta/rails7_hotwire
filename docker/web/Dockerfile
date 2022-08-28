FROM ruby:3.1

WORKDIR /work
COPY Gemfile /work/Gemfile
COPY Gemfile.lock /work/Gemfile.lock
RUN bundle install
COPY . /work

# Add a script to be executed every time the container starts.
COPY ../../entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
EXPOSE 3000

# Start the main process.
CMD ["rails", "server", "-b", "0.0.0.0"]
