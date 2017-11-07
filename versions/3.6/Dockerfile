FROM python:3.6-slim

COPY locales.txt /etc/locale.gen

# provisioning, without gdal
RUN apt-get -qq update \
    && apt-get install -y --no-install-recommends \
        wget git-core tmux vim locales less \
        binutils \
    && rm -rf /var/lib/apt/lists/* \
    && echo 'alias ll="ls -l"' >> ~/.bashrc \
    && echo 'alias la="ls -la"' >> ~/.bashrc \
    && locale-gen

# upgrade pip
RUN pip3 install --upgrade pip

# initialize app
RUN mkdir -p /app
WORKDIR /app

