FROM postgres:12.3
RUN apt-get update && apt-get install -y make git
RUN mkdir "/pgjwt"
WORKDIR "/pgjwt"
COPY . .
RUN make && make install