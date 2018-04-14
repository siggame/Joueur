FROM python:slim-stretch
ENV TINI_VERSION v0.17.0
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN groupadd -r siggame && useradd -r -g siggame siggame \
    && mkdir /client && chown -R siggame:siggame /client \
    && chmod +x /tini
WORKDIR /client

ENTRYPOINT ["/tini", "--", "venv/bin/python", "-u", "main.py"]
