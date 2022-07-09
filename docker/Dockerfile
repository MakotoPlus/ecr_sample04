FROM python:3.8
USER root


ENV DOCKER_DIR="./docker"
ENV COPY_SOURCE_DIR="./projects"
ENV SOURCE_DIR="./projects"

RUN apt-get update
RUN apt-get -y install locales && \
    localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ JST-9
ENV TERM xterm
RUN apt-get install -y vim less

# コンテナ側へコピー
COPY $DOCKER_DIR/requirements.txt requirements.txt

# ソースを正式場所へコピー
# COPY $COPY_SOURCE_DIR $SOURCE_DIR

# python ライブラリインストール
RUN pip install -r ./requirements.txt

# WORKDIR $SOURCE_DIR/myproject
# CMD ["python", "manage.py", "runserver", "0.0.0.0:80"]


