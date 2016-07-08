FROM solr:6.1

ENV reposIndexingVersion master
ENV xmlIndexingVersion master

RUN cd server/solr \
  && curl -SL https://github.com/Reposoft/repos-indexing/archive/$reposIndexingVersion.tar.gz -o repos-indexing.tar.gz \
  && tar xvzf repos-indexing.tar.gz --strip-components=8 repos-indexing-$xmlIndexingVersion/src/main/resources/se/repos/indexing/solr/repositem \
  && rm repos-indexing.tar.gz

RUN cd server/solr \
  && curl -SL https://github.com/Simonsoft/cms-indexing-xml/archive/$xmlIndexingVersion.tar.gz -o cms-indexing-xml.tar.gz \
  && tar xvzf cms-indexing-xml.tar.gz --strip-components=10 cms-indexing-xml-$xmlIndexingVersion/src/main/resources/se/simonsoft/cms/indexing/xml/solr/reposxml \
  && rm cms-indexing-xml.tar.gz
