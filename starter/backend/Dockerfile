FROM python:3.10-slim

ENV PYTHONUNBUFFERED=1
ENV FLASK_RUN_HOST=0.0.0.0

WORKDIR /

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    build-essential \
    libpcre2-dev \
    libssl-dev \
    libffi-dev \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir pipenv

COPY Pipfile Pipfile.lock /app/

RUN cd /app && pipenv install --system --deploy

COPY . /app/backend

EXPOSE 5000

CMD ["uwsgi", "--http", ":5000", "--master", "--enable-threads", "--chdir", "/app", "--module", "backend:app"]