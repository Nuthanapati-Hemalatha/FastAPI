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

shutil in Python: shutil is a standard library module in Python used for file operations — such as copying, moving, or deleting files and directories.

shutil.copyfile(src, dst): Copies file contents from src to dst
shutil.copytree(src, dst): Copies an entire directory tree
shutil.rmtree(path):	Deletes a directory tree
shutil.move(src, dst):	Moves (or renames) a file or directory
shutil.copyfileobj(src, dst):	Copies content from one file object to another

Pandas: Data analysis library in python. 
Why use pandas?
Easily read CSV, Excel, JSON, etc.
Clean and analyze data (filter rows, sort, group, etc.)
Work with rows and columns like a spreadsheet
Very fast and great for working with big data

2 DATA STRUCTURES:
(A)SERIES   (B)DATAFRAME
SERIES: one-dimensional labeled array capable of holding any data type
DATAFRAME: two-dimensional labeled data structure with columns of potentially different types
include='all' for mixed datatypes we will use

DESCRIPTIVE STATISTICS: used to quickly summarize and describe the basic features of a dataset. 
It helps to understand distribution, central tendency, spread and shape of your data
map():  For Single Column (Series) when you want to change each value in one column
apply(): For Columns, Rows, or a Series
Handling missing data:
df.isnull()           # Shows True where data is missing
df.isnull().sum()     # Total missing values per column

df.dropna()         Remove rows with missing values
df.dropna(axis=1)   Remove columns with missing values
df.fillna(0)          # Replace all missing with 0
df['Marks'].fillna(df['Marks'].mean())  Fill with column avg
df.fillna(method='ffill')   # Forward fill
df.fillna(method='bfill')   # Backward fill

Indexing, Slicing & Filtering:
s.iloc[]: Purely integer location based indexing
s.loc[]: Labelbased indexing
s[s>n]: Filetrs and returns elements return FileResponse(file_path, media_type='application/octet-stream', headers={"Content-Disposition": f"attachment; filename={filename}"})gretaer than n
s.aggregate(func): Aggregate using one or more operations

DataFrame: A DataFrame is a two-dimensional (tabular) data structure in Pandas. It’s like a spreadsheet or SQL table — rows and columns of data.
df.head(10) display starting 10 rows
df.tail(10) display ending 10 rows
df.shape() - no.of rows & no. of columns
df.columns List all column names in the DataFrame
df.dtypes display the data types of each column

diff b/w map and apply function:
map:Works only on Series (i.e., one column).
Applies a function to each value in the Series.
Simpler, faster, and used for element-wise operations.
apply() function
Works on both Series and DataFrames.
More powerful and flexible.
Can apply a function row-wise or column-wise (on multiple columns).





{Orient parameter tells how to structure the dictionary}
