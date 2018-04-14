FROM python:slim-stretch

RUN mkdir -p /usr/src/client \
    && apt-get update \
    && apt-get install -y \
    gcc \
    git \    
    && git clone https://github.com/siggame/Joueur.py.git /usr/src/assets \
    && cp /usr/src/assets/requirements.txt /usr/src/client \
    && cd /usr/src/client \
    && python -m venv venv \
    && until [ -f venv/bin/activate ]; do sleep 1; done \
    && venv/bin/pip install --no-cache-dir -r requirements.txt
WORKDIR /usr/src/client

ONBUILD COPY requirements.txt .
ONBUILD RUN venv/bin/pip install --no-cache-dir -r requirements.txt

ONBUILD COPY . .
