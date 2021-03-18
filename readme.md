### Logging with Python
This study of logging with python was provided by Real Python in this link:
https://realpython.com/python-logging-source-code/


### Importants Concepts
logging in python is specified inside Python 3.7 Cpython repos, Specially in the commit  
https://github.com/python/cpython/tree/d730719b094cb006711b1cd546927b863c173b31.  
Within the logging package, most of the heavy lifting occurs within logging/__init__.py, which is the file you’ll spend the most time on here:  
│  
├── Lib/  
│   ├── logging/  
│   │   ├── __init__.py  
│   │   ├── config.py  
│   │   └── handlers.py  
│   ├── ...  
├── Modules/  
├── Include/  
...  
... [truncated]  

### The LogRecord Class
What is a LogRecord? When you log a message, an instance of the LogRecord class is the object you send to be logged. It’s created for you by a Logger instance and encapsulates all the pertinent info about that event. Internally, it’s little more than a wrapper around a dict that contains attributes for the record. A Logger instance sends a LogRecord instance to zero or more Handler instances.

The LogRecord contains some metadata, such as the following:

A name  
The creation time as a Unix timestamp  
The message itself  
Information on what function made the logging call  
