# DJANGO-VARCEL

##SETUP 
- buat file varcel.json (berada sejajar dengan file manage.py)
```
{
    "builds": [{
        "src": "djangoprojectname/wsgi.py",
        "use": "@vercel/python",
        "config": { "maxLambdaSize": "15mb", "runtime": "python3.9" }
    }],
    "routes": [
        {
            "src": "/(.*)",
            "dest": "djangoprojectname/wsgi.py"
        }
    ]
}
```
- setting allowed host dengan nama vercel (berada di file settings.py)
   ```
   ALLOWED_HOSTS = ['.varcel.app']
   ```
- register app di wsgi.py, (berada sejajar dengan file settings.py)

  ```
  app = application
  ```
- buat file requirements.txt
  ```
  pip freeze > requirements.txt
  ```
