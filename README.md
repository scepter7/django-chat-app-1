-------------Follow these steps to get the servers working (tested in python 3.6.0)------------------  
  
create a file called .env  
copy contents of sample.env to .env  
  
```
python -m pip install -U -r "requirements.txt"
```
```
python -m pip install -U south
```
```
python -m pip install -U django-extensions
```
```
python -m pip install -U django-crispy-forms
```
  
db.sqlite3  
```
python manage.py makemigrations chat
```
```
python manage.py makemigrations home
```
```
python manage.py migrate
```
  
To start the chat server  
```
python manage.py runserver
```
  
To start the chat (websocket) server  
```
python manage.py run_chat_server
```
  
open multiple chat sessions in chrome, in incognito and in another browser say firefox  
```
http://127.0.0.1:8000/
```
  
Use hostname instead of 127.0.0.1  
 edit ChatBot/settings.xml  
  ```
  ALLOWED_HOSTS = ['hangouts.com']
  CHAT_WS_SERVER_HOST = values.Value('hangouts.com')
  ```
 edit .env  
  ```
  DJANGO_ALLOWED_HOSTS="hangouts.com"
  DJANGO_CHAT_WS_SERVER_HOST="hangouts.com"
  ```
open chat sessions using http://hangouts.com:8000/  
