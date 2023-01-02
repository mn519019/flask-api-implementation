## REST API 
- GET: Retriee
- Post: Write new data
- Delete: Delete junk
- PUT: Write update data
- Rest requires to implement CRUD (Create, Read, Update, and Delete)

## Project
- This project is to implement a simple concept of api_example.py by adopting stackoverflow webpages.

## Python Virtual Environment (Required)
```
# The own virtual environment isolates the process 
# python3 -m venv /path/to/new/virtual/environment
$ python3 -m venv .venv
$ source .venv/bin/activate

# Install Required packages 
(.venv) pip3 install flask 
(.venv) pip3 install flask-sqlalchemy

# Run Flask 
(.venv) export FLASK_APP=applictions.py
(.venv) export FLASK_ENV=development
(.venv) flask run
```
## Instructions 
```
## Check the /drinks json data 
Hello(.venv) Rickys-MacBook-Pro:rest-api rickyyang$ curl localhost:5000/drinks
{
  "drinks": [
    {
      "description": "Taste just like that",
      "name": "Grape Soda"
    },
    {
      "description": "Taste like Cherry",
      "name": "Cherry"
    }
  ]
}
## Get the first data using 'id'
## id=1 
(.venv) Rickys-MacBook-Pro:rest-api rickyyang$ curl localhost:5000/drinks/1
{
  "description": "Taste just like that",
  "name": "Grape Soda"
}
## Add new data using a 'POST' method
$ curl -v -H "Content-Type: application/json" -X POST      -d '{"name": "Blackberry","description": "my fav!"}' http://127.0.0.1:5000/drinks

Rickys-MacBook-Pro:~ rickyyang$ curl localhost:5000/drinks/3
{
  "description": "my fav!",
  "name": "Blackberry"
}

## Delete data using a 'DELETE' method
$ curl -X DELETE http://127.0.0.1:5000/drinks/3 -H "Accept: application/json"
{
  "message": "Deleted id:3"
}
$ curl localhost:5000/drinks/3
<!doctype html>
<html lang=en>
<title>404 Not Found</title>
<h1>Not Found</h1>
<p>The requested URL was not found on the server. If you entered the URL manually please check your spelling and try again.</p>
```