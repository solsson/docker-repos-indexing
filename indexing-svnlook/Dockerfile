# Same base as https://hub.docker.com/_/solr/ 6.1
FROM java:openjdk-8-jre

# TODO optimize layers
RUN apt-get update
RUN apt-get install -y openjdk-8-jdk-headless maven git
RUN git clone https://github.com/Reposoft/repos-indexing-standalone
RUN cd repos-indexing-standalone && mvn package

# TODO get tagged release, can use curl
# TODO remove .m2
# openjdk-8-jdk-headless needed for tools.jar, though maven depends on openjdk-7
RUN mv repos-indexing-standalone/target/repos-indexing-standalone-jar-with-dependencies.jar repos-indexing-standalone-jar-with-dependencies.jar

ENTRYPOINT java -jar repos-indexing-standalone-jar-with-dependencies.jar 
