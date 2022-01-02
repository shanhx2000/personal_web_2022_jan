# Develop Personal Website

```bash
# Tutorial: https://medium.com/@francescaguiducci/how-to-build-a-simple-personal-website-with-python-flask-and-netlify-d800c97c283d
# Flask: https://flask.palletsprojects.com/en/2.0.x/quickstart/
```

## Install Flask

```bash
# Ref: https://flask.palletsprojects.com/en/2.0.x/installation/#python-version
# https://pythonhosted.org/Frozen-Flask/
```

```bash
mkdir myproject
cd myproject
python3 -m venv venv
. venv/bin/activate
pip install Flask # Main
pip install Frozen-Flask # Frozen-Flask
```

## Run Flask

```bash
export FLASK_APP=hello # Suppose hello.py
# export FLASK_ENV=development
# export FLASK_ENV=production # Default
flask run
```

## Notes

### Functions

#### `escape()`

Any user-provided values rendered in the output must be escaped to protect from injection attacks

```python
from markupsafe import escape
@app.route("/<name>")
def hello(name):
    return f"Hello, {escape(name)}!"
```

#### `route()'

Decorator to bind a function to a URL

#### `<converter:variable_name>`

Converter types

| Types | Details |
| --- | --- |
| string | (default) accepts any text without a slash |
| int | accepts positive integers |
| float | accepts positive floating point values |
| path | like string but also accepts slashes |
| uuid | accepts UUID strings |

#### URL for Static Files

To generate URLs for static files, use the special 'static' endpoint name:

```python
url_for('static', filename='style.css')
```

The file has to be stored on the filesystem as static/style.css.

## Jinja2 Templetes

```
Case 1: a module
/application.py
/templates
    /hello.html

Case 2: a package
/application
    /__init__.py
    /templates
        /hello.html
```

## Netlify

### Requirements

```
pip freeze > requirements.txt
```
