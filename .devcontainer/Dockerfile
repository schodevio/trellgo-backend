# Make sure GO_VERSION matches the Go version you want to use
ARG GO_VERSION=1.25
FROM mcr.microsoft.com/devcontainers/go:$GO_VERSION

USER root

# Install packages needed to build gems
# RUN apt-get update -qq && \
#     apt-get install --no-install-recommends -y pkg-config

# --- Custom setup
USER vscode

RUN git clone https://github.com/zsh-users/zsh-autosuggestions \
    ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

RUN sed -ir 's/plugins=(git)/plugins=(git zsh-autosuggestions)/g' ~/.zshrc && \
    sudo chsh -s $(which zsh) $(whoami)
# ---
