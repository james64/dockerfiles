FROM alpine

RUN apk --update add curl openjdk11-jre git

RUN curl -s -Lo /bin/coursier https://git.io/coursier-cli
RUN chmod +x /bin/coursier

RUN echo "coursier launch -q -r 'https://jcenter.bintray.com' com.github.james64:reckon-standalone:0.0.1 -- \$@" > /bin/reckon
RUN chmod +x /bin/reckon

# first run to download deps and store them in image
RUN reckon --help

COPY helm2 /bin/helm

ENTRYPOINT /bin/sh -c
