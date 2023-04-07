FROM openjdk:17-jdk-bullseye

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    wget \
    curl \
    unzip \
    gnupg \
    software-properties-common \
    ca-certificates apt-transport-https lsb-release \
    && rm -rf /var/lib/apt/lists/*

# Install Maven
ARG MAVEN_VERSION=3.9.1
RUN wget https://dlcdn.apache.org/maven/maven-3/${MAVEN_VERSION}/binaries/apache-maven-${MAVEN_VERSION}-bin.tar.gz -P /tmp && \
    tar xf /tmp/apache-maven-${MAVEN_VERSION}-bin.tar.gz -C /opt && \
    ln -s /opt/apache-maven-${MAVEN_VERSION}/bin/mvn /usr/local/bin/mvn && \
    rm /tmp/apache-maven-${MAVEN_VERSION}-bin.tar.gz

# Install Gradle
ARG GRADLE_VERSION=8.0.2
RUN wget https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip -P /tmp && \
    unzip /tmp/gradle-${GRADLE_VERSION}-bin.zip -d /opt && \
    ln -s /opt/gradle-${GRADLE_VERSION}/bin/gradle /usr/local/bin/gradle && \
    rm /tmp/gradle-${GRADLE_VERSION}-bin.zip
