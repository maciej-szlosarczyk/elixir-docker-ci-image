FROM cimg/elixir:1.14-browsers

# Install ssh-askpass
RUN wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
RUN sudo apt-get update && sudo apt-get install -y ssh-askpass
RUN [ -d ~/.ssh ] || mkdir ~/.ssh && chmod 0700 ~/.ssh
RUN ssh-keyscan -t rsa,dsa github.com >> ~/.ssh/known_hosts

# Install Chrome and Chromedriver
COPY ./../.docker_scripts .docker_scripts
RUN ./.docker_scripts/install-chrome.sh
RUN ./.docker_scripts/install-chromedriver.sh
