# Understanding_Flask
##  What is Flask ?
 - Flask is a web application framework in ***python***
 - Flask depends on the ***Jinja template engine*** and the ***Werkzeug WSGI toolkit.***
## Installation 
 - I recommend using the latest version of Python 3. Flask supports Python 3.5 and newer.
### Virtual environments
 - What problem does a virtual environment solve? The more Python projects you have, the more likely it is that you need to work with different versions of Python libraries, or even Python itself. Newer versions of libraries for one project can break compatibility in another project.

 - Virtual environments are independent groups of Python libraries, one for each project. Packages installed for one project will not affect other projects or the operating system’s packages.

 - Python 3 comes bundled with the venv module to create virtual environments. 
### Create an environment
#### Create a project folder and a venv folder within:
    $ mkdir project1
    $ cd project1
    $ pip install virtualenv
    $ virtualenv env 
          OR
    py -m virtualenv env
#### Activate the environment
    >env\Scripts\activate 
        OR
    source env/Scripts/activate
#### Install Flask
      $ pip install Flask
## A minimal Flask application looks something like this:
    
       from flask import Flask
       app = Flask(__name__)

       @app.route('/')
       def hello_world():
            return 'Hello, World!'
       
       
     if __name__ == "__main__":
          app.run(debug=True)

 ### So what did that code do?
 - First we imported the Flask class. An instance of this class will be our WSGI application.

 - Next we create an instance of this class. The first argument is the name of the application’s module or package. If you are using a single module (as in this example), you should use __name__ because depending on if it’s started as application or imported as module the name will be different ('__main__' versus the actual import name). This is needed so that Flask knows where to look for templates, static files, and so on. 

 - We then use the route() decorator to tell Flask what URL should trigger our function.

 - The function is given a name which is also used to generate URLs for that particular function, and returns the message we want to display in the user’s browser.
***Just save it as hello.py or something similar. Make sure to not call your application flask.py because this would conflict with Flask itself.***
