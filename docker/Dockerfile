FROM python:3.6-alpine3.7
RUN apk add --update tini build-base git jpeg-dev zlib zlib-dev

RUN mkdir /bot
COPY . /bot
WORKDIR /bot

ENV LIBRARY_PATH=/lib:/usr/lib

RUN pip install pipenv
RUN pipenv install --deploy --system

ENTRYPOINT ["/sbin/tini", "--"]
CMD ["python", "-m", "bot"]

