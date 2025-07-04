Flasky
======

This repository contains the source code examples for the second edition of my O'Reilly book [Flask Web Development](http://www.flaskbook.com).

The commits and tags in this repository were carefully created to match the sequence in which concepts are presented in the book. Please read the section titled "How to Work with the Example Code" in the book's preface for instructions.

For Readers of the First Edition of the Book
--------------------------------------------

The code examples for the first edition of the book were moved to a different repository: [https://github.com/miguelgrinberg/flasky-first-edition](https://github.com/miguelgrinberg/flasky-first-edition).

---

Flask Cheatsheet
======

Boilerplate Code
```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"

app.run()
```
- app.route decorator - used to map request URL to a flask view function in the application

Help command 
```python
flask --help 
```
Export flask application as an environment variable
```python
export FLASK_APP=hello.py
```
Enable debugging mode - set environment variable
```python
export FLASK_DEBUG=1
```
Run application
```python
flask run 
```
Run flask application on a specific port flask 
```python
run -p 5001
```
---
[Address already in use ports](https://flask.palletsprojects.com/en/stable/server/#address-already-in-use)

List the details of the process using port 5000. You can then terminate the process if necessary. 
```python
lsof -i :5000 
```
Terminate the occupying process using the PID provided in the command above
```python
kill -9 [PID] 
```

---
Jinja2
--------------------------------------------
Jinja2 is a template engine that lets you embed Python like logic into HTML to dynamically render web pages. It supports features like variables, control structures (such as loops and conditionals), template inheritance, and filters to create flexible and reusable templates.

app.py
```python
app = Flask(__name__)

@app.route('/')
def home():
    return render_template('hello.html', name='Elliot')
```
templates/hello.html
```html
<!doctype html>
<html>
  <body>
    <h1>Hello, {{ name }}!</h1>
  </body>
</html>
```
