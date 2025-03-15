FROM ruby:3.2-bullseye

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=1000

# Install dependencies
RUN apt-get update && apt-get install -y build-essential git && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Create a non-root user
RUN groupadd --gid $USER_GID $USERNAME && \
    useradd --uid $USER_UID --gid $USER_GID -m $USERNAME

# Set working directory (VS Code uses /workspaces by default)
WORKDIR /workspaces

# Switch to the non-root user
USER $USERNAME