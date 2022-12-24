FROM python

ENV PYTHONDONTWRITEBYTECODE 1 # Prevent writing .pyc files

ENV PYTHONUNBUFFERED 1 # Prevent buffering

WORKDIR /app 

COPY . /app

RUN apt update ; apt upgrade -y; apt install git wget curl -y

ARG USER_ID

ARG GROUP_ID

RUN addgroup --gid $GROUP_ID user

RUN adduser --disabled-password --gecos '' --uid $USER_ID --gid $GROUP_ID user

USER user

RUN pip3 install --upgrade -U  -r requirements.txt  --no-cache-dir

EXPOSE 8000

CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]