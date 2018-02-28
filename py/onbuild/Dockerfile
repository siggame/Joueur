FROM python:latest

RUN mkdir -p /usr/src/client \
    && git clone https://github.com/siggame/Joueur.py.git /usr/src/assets \
    && cp /usr/src/assets/requirements.txt /usr/src/client \
    && cd /usr/src/client \
    && pip install --no-cache-dir -r requirements.txt
WORKDIR /usr/src/client

ONBUILD COPY requirements.txt .
ONBUILD RUN pip install --no-cache-dir -r requirements.txt

ONBUILD COPY . .
