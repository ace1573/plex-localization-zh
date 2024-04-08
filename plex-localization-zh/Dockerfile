FROM python:3.9-slim-buster

ARG PLEX_HOST 
ARG PLEX_TOKEN
ARG SKIP_LIBS

ENV PLEX_HOST=${PLEX_HOST} PLEX_TOKEN=${PLEX_TOKEN} SKIP_LIBS=${SKIP_LIBS}

WORKDIR /usr/src

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

COPY . .

CMD ["python3", "plex-localization-zh.py"]
