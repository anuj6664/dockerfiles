FROM ubuntu:jammy-20260509

#create directory
RUN mkdir -p /opt/app

#set working directory
WORKDIR /opt/app

#copy java jdk
ADD jdk-21_linux-x64_bin.tar.gz .
ADD maven-mvnd-1.0.5-linux-amd64.tar.gz .
# Create non-root user
RUN useradd -u 1000 -m -d /home/appuser appuser

# Set permissions
RUN chown -R appuser:appuser /opt/app

# Switch user
USER appuser

# Set Java environment
ENV JAVA_HOME=/opt/app/jdk-21.0.11
ENV PATH="${JAVA_HOME}/bin:${PATH}"
ENV M2_HOME=/opt/app/maven-mvnd-1.0.5-linux-amd64/mvn
ENV PATH="${M2_HOME}/bin:${PATH}"

CMD ["bash"]
~
