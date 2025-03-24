"FastAPI is a high-performance, modern web framework for building APIs with Python. It is designed to be fast, easy to use, and supports asynchronous programming. We use FastAPI because it provides automatic validation using Python type hints, built-in API documentation, and better performance compared to traditional frameworks like Flask. It is ideal for microservices, machine learning APIs, and high-performance applications."

FastAPI is a Python web framework designed for building fast, efficient, and scalable APIs.

It is based on Starlette (for web handling) and Pydantic (for data validation).
 
Supports both synchronous & asynchronous programming (using async/await).

Automatically generates interactive API documentation (Swagger & ReDoc).

Why we use?
 High Performance → Nearly as fast as Node.js & Go 🚀
✔ Asynchronous Support → Handles multiple requests efficiently ⚡
✔ Automatic API Documentation → Swagger UI & ReDoc 📄
✔ Type Safety with Pydantic → Reduces runtime errors ✅
✔ Minimal Boilerplate Code → Faster development 📝
✔ Built-in Dependency Injection → Clean and scalable architecture 

Synchronous execution:
In synchronous programming, each request is processed one at a time, blocking execution until completion.
If a request takes time the server waits before handling the next request.
Ex: Sync → Heavy CPU tasks like image processing

from fastapi import FastAPI
import time

app = FastAPI()

@app.get("/sync")
def sync_task():
    time.sleep(3)  # Simulating a slow task
    return {"message": "Synchronous response"}


Asynchronous Execution:
Allows the server to handle multiple requests concurrently using async/await.
It is non-blocking, meaning while one task waits, another request can be processed.
Ex: Async → Database calls, HTTP requests

from fastapi import FastAPI
import asyncio

app = FastAPI()

@app.get("/async")
async def async_task():
    await asyncio.sleep(3)  # Simulating a slow I/O task
    return {"message": "Asynchronous response"}

**Path parameters:**
Path parameters allow us to pass dynamic values in the URL.
They are defined using {parameter_name} inside the route path.
FastAPI automatically converts them to the specified data type and performs validation.
Path parameters in FastAPI are variables embedded in the URL that allow dynamic data retrieval.
They are defined using curly braces {} in the route path and passed as function arguments.

**Query parameters:**
Query parameters are optional parameters included in the URL after ?.
They are not part of the path but are used for filtering, searching, or modifying requests.
Defined as function arguments with default values.

**POST Endpoint: **
A POST endpoint in FastAPI is used to send data to the server, usually for creating new resources.
It accepts request bodies in JSON format, validates the input using Pydantic models, and returns a response.

**Automatic Documentation:**
FastAPI automatically generates API documentation using OpenAPI.
Provides two UI options:
Swagger UI 
ReDoc
No extra configuration is needed.
Uses Python type hints & Pydantic models to generate API docs.

**PUT & DELETE END POINS:**
PUT: Used to update an existing resource. It replaces the entire resource.
DELETE: Used to remove a resource from server.
FastAPI provides automatic request validation using Pydantic models.

**Pydantic schemas and validation:**
Pydantic in FastAPI used for data validation and serialization.
It ensures request data is valid by enforcing types and constraints using Python type hints.
Improves API reliability & security.
Pydantic Model is created using Base Model
Pydantic automatically handles errors and provides clear messages.

HTTP Exceptions:
Allow us to return error responses with specific HTTP status codes using HTTPException.
This helps in handling invalid requests, authentication failures, and other errors in a structured way.

