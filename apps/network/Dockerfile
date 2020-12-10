FROM anibali/pytorch:1.5.0-cuda10.2
USER root
#RUN mkdir /app
WORKDIR /app

RUN apt-get update
RUN apt install -y build-essential
#RUN apt-get install -y git python3-pip
#RUN pip3 install --upgrade pip

RUN pip install poetry
COPY poetry.lock pyproject.toml entrypoint.sh /app/
COPY /src /app/src
WORKDIR /app/
RUN poetry install

ENTRYPOINT ["sh", "entrypoint.sh"]
