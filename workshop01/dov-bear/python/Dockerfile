FROM python:latest

LABEL "name" = "jl_app"

ARG APP_DIR=/app

RUN mkdir $APP_DIR

WORKDIR $APP_DIR

ADD main.py .
ADD utils.py .
ADD requirements.txt .
ADD public public
ADD templates templates

RUN pip install  -r requirements.txt


ENV PORT=5000
ENV INSTANCE_NAME=instanceeename
ENV INSTANCE_HASH=instancebrownpotato

HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
CMD curl http://localhost:${PORT}/healthz
EXPOSE $PORT


ENTRYPOINT ["python", "./main.py"]
CMD [$PORT]