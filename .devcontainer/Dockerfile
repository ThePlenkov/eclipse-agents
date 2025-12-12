# Devcontainer Dockerfile using Eclipse Temurin Java 17
FROM eclipse-temurin:17-jdk

# Create a non-root user 'vscode' if not provided by the base
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN apt-get update \
  && apt-get install -y --no-install-recommends git curl ca-certificates \
  && rm -rf /var/lib/apt/lists/*

# Ensure maven is available
RUN apt-get update && apt-get install -y maven && rm -rf /var/lib/apt/lists/*

# Create user
RUN groupadd --gid $USER_GID $USERNAME || true \
  && useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME || true

USER $USERNAME
WORKDIR /workspaces/eclipse-agents
