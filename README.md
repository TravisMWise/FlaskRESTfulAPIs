# Flask RESTful API Application

```
GET	    http://[hostname]/todo/api/v1.0/tasks	        Retrieve list of tasks
GET	    http://[hostname]/todo/api/v1.0/tasks/[task_id]	Retrieve a task
POST	http://[hostname]/todo/api/v1.0/tasks	        Create a new task
PUT	    http://[hostname]/todo/api/v1.0/tasks/[task_id]	Update an existing task
DELETE	http://[hostname]/todo/api/v1.0/tasks/[task_id]	Delete a task

id: unique identifier for tasks. Numeric type.
title: short task description. String type.
description: long task description. Text type.
done: task completion state. Boolean type.
```

Test using Curl:
```
Get Request: 
    curl -i http://localhost:5000/todo/api/v1.0/tasks
Response:
    HTTP/1.1 200 OK
    Server: Werkzeug/2.3.6 Python/3.10.8
    Date: Thu, 13 Jul 2023 19:58:51 GMT
    Content-Type: application/json
    Content-Length: 334
    Connection: close

    {
    "tasks": [
        {
        "desc": "Batman costume screen matched to the movie the Dark Knight.",
        "done": false,
        "id": 1,
        "title": "Batman Costume"
        },
        {
        "desc": "Joker costume screen matched to the movie the Dark Knight.",
        "done": false,
        "id": 2,
        "title": "Joker Costume"
        }
    ]
    }

Post Request: 
    curl -i -H "Content-Type: application/json" -X POST -d "{"""title""":"""Test"""}" http://localhost:5000/todo/api/v1.0/tasks
```