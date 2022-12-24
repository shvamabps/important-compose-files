- Need an existing Django project with requirements.txt to run the application
- Working dir is `/app`
- Everything in `.` or `$PWD` is copied to `/app` in the container
- `PORT` is Django default port
- Command to build a new image `docker build -t django-starter   --build-arg USER_ID=$(id -u) --build-arg GROUP_ID=$(id -g) .`
- If an app is created inside the container it is editable outside the container too.
- Example `compose` file

```
version: "3.9"
services:
  web:
    image: shvamabps/django
    command: >
      sh -c "python manage.py makemigrations --noinput &&
             python manage.py migrate &&
             python manage.py runserver 0.0.0.0:8000"
    ports:
      - "8000:8000"
    volumes:
      - .:/app
    restart: always
```
