- Need an existing Django project with requirements.txt to run the application
- Working dir is `/app`
- Everything in `.` or `$PWD` is copied to `/app` in the container
- `PORT` is Django default port
- Example command:

```
docker run -it -d -v $PWD:/app -p 8000:8000 --name test  shvamabps/django-starter
```

- If an app is created inside the container it is editable outside the container too.
