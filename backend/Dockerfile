FROM python:3.8-alpine
ENV PYTHONUNBUFFERED=1
WORKDIR /django
COPY requirements.txt requirements.txt
COPY ../.env ../.env

# Update and install packages
RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev libpq-dev
RUN pip install -r requirements.txt