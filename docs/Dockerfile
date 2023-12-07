FROM jekyll/jekyll:latest
COPY Gemfile Gemfile.lock /srv/jekyll/
RUN bundle install
CMD bundle exec jekyll serve
