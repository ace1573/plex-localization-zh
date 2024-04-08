FROM python:3.9-slim-buster

#服务器地址和token
ARG PLEX_HOST 
ARG PLEX_TOKEN
#跳过媒体库，中文分号隔开
ARG SKIP_LIBS
#循环间隙
ARG LOOP_INTERVAL=600

ENV PLEX_HOST=${PLEX_HOST} PLEX_TOKEN=${PLEX_TOKEN} SKIP_LIBS=${SKIP_LIBS} LOOP_INTERVAL=${LOOP_INTERVAL}

WORKDIR /usr/src

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

COPY . .

CMD ["python3", "plex-localization-zh.py"]


#build: docker build --tag plex-zh-plugin .
#run: docker run -e PLEX_HOST="https://localhost:32400" -e PLEX_TOKEN="xxx" plex-zh-plugin

