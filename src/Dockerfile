ARG REGISTRY=yann-swampup.dev.aws.devopsacc.team
ARG DOCKER_REPO=urs-docker
ARG PYTHON_REPO=urs-python

FROM ${REGISTRY}/${REPO}/python:3.9.5-slim-buster

WORKDIR  /var/opt/webapp

RUN mkdir -p /var/opt/webapp
ADD webapp_python.tar.gz . 
RUN pip config set global.index-url https://$REGISTRY/artifactory/api/pypi/${PYTHON_REPO}/simple && \
    pip install -r requirements.txt

EXPOSE 8080

ENTRYPOINT ["python3", "main.py"]
