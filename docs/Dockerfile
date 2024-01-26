FROM jekyll/jekyll:latest
COPY Gemfile Gemfile.loc[k] /srv/jekyll/
RUN bundle install
CMD bundle exec jekyll serve
