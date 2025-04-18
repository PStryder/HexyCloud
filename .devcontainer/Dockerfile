# Use an official Node base image
FROM mcr.microsoft.com/devcontainers/javascript-node:18

# Install Java (OpenJDK 17)
RUN apt-get update \
  && apt-get install -y openjdk-17-jdk \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

# Set JAVA_HOME for Firebase Emulator compatibility
ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
ENV PATH="$JAVA_HOME/bin:$PATH"

# Install Python + pip + venv support
RUN apt-get update \
  && apt-get install -y python3 python3-pip python3-venv \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

# Install Firebase CLI globally
RUN npm install -g firebase-tools

# Setup working directory
WORKDIR /workspace

# Default shell
CMD ["/bin/bash"]
