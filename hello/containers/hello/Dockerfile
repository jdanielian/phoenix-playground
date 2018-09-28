# Elixir + Phoenix

FROM elixir:1.7

ENV APP_HOME=/app

# Install debian packages
RUN apt-get update
RUN apt-get install --yes build-essential inotify-tools postgresql-client
#Copy the source folder into the Docker image
ADD . $APP_HOME

WORKDIR $APP_HOME

# Install Phoenix packages
RUN mix local.hex --force
RUN mix local.rebar --force
RUN mix archive.install --force https://github.com/phoenixframework/archives/raw/master/phx_new.ez

# Install node
RUN curl -sL https://deb.nodesource.com/setup_6.x -o nodesource_setup.sh
RUN bash nodesource_setup.sh
RUN apt-get install nodejs

#COPY . $APP_HOME

EXPOSE 4000