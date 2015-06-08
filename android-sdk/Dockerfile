FROM cgcgbcbc/oracle-java-8

RUN apt-get update && \
    apt-get -y install lib32stdc++6 lib32z1 && \
    wget http://dl.google.com/android/android-sdk_r24.2-linux.tgz
RUN tar -C /usr/local -xzf android-sdk_r24.2-linux.tgz

RUN (while :; do echo 'y'; sleep 2; done) | /usr/local/android-sdk-linux/tools/android update sdk --filter platform,tool,platform-tool,extra,build-tools-22.0.1 --no-ui --force -a

RUN rm android-sdk_r24.2-linux.tgz

