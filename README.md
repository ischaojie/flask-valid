# flask-valid

`flask-valid` is a Flask request and response validator use pydantic.

Basically, you just need add `validator` decorator to your view function,
`flask-valid` will auto validate params data and rsponse data for you.

It's kind of like famous library `FastAPI`, bring part of brilliant features of `FastAPI` to your Flask application.

## Feature

-   Intuitive and easy to use.
-   Use type hinting to validate path + query + body params.

## Quick start

```bash
pip install flask-valid
```

After that, you can import `validator` from `flask_valid`, and use it in your `views`.

A simple example:

```python
from flask import Flask
from pydantic import BaseModel
from flask_valid import validator

app = Flask(__name__)


@app.get("/books/<id>/")
@validator
def home(id:int, q: str, star: float=10):
    return {"id":id, "q": q, "star": star}

if __name__ == "__main__":
    app.run(debug=True)

```

## License

This project is licensed under the terms of the MIT license.
