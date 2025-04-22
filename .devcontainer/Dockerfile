FROM mcr.microsoft.com/devcontainers/universal:2-linux
# Install the xz-utils package
RUN apt-get update && \
    pip install django

RUN apt-get update && apt-get install -y xz-utils
RUN pip install flask
RUN npm install -g @vue/cli
RUN pip install flask flask-cors
