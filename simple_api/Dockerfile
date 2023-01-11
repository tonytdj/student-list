FROM python:2.7-stretch AS build
LABEL Tony "tony@dejesus.pt"
RUN git clone https://github.com/diranetafen/student-list.git
RUN apt-get update -y && apt-get install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y
RUN pip install flask==1.1.2 flask_httpauth==4.1.0 flask_simpleldap python-dotenv==0.14.0
COPY student-list /




FROM alpine:latest AS test
WORKDIR /root/
COPY --from=base /go/src/github.com/alexellis/href-counter/app ./
CMD ["./app"]