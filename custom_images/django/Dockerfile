FROM python

ENV PYTHONDONTWRITEBYTECODE 1 # Prevent writing .pyc files

ENV PYTHONUNBUFFERED 1 # Prevent buffering

WORKDIR /app 

RUN apt update ; apt upgrade -y; apt install git wget curl -y

ARG USER_ID

ARG GROUP_ID

RUN addgroup --gid $GROUP_ID user

RUN adduser --disabled-password --gecos '' --uid $USER_ID --gid $GROUP_ID  --shell /bin/bash  user 

USER user

RUN pip3 install --upgrade -U django djangorestframework psycopg2 django-cors-headers  --no-cache-dir

EXPOSE 8000
