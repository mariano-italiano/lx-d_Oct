# Create container image from base image ubuntu:20.04
FROM ubuntu:20.04

# Create group with GID 2500 and user with UID 2500
RUN groupadd -g 2500 appgroup && \
    useradd -m -u 2500 -g appgroup appuser

# Run container image as user 'appuser'
USER appuser

# Define workdir
WORKDIR /home/appuser

#CMD ["sh", "-c", "echo 'Running my first container with user' $(whoami) 'UID= '$(id -u)"]
ENTRYPOINT ["/bin/bash"]
CMD ["-c", "tail -f /dev/null"]

