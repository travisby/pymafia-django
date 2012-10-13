pymafia-django
==============

Django Project for pymafia


How to run
----------

### Notes

We tried our best to follow the [12 Factor App][http://www.12factor.net/] the best we could.  This means that configuration variables live in the user's environment.  I have a ".env" file that gets loaded before I run Django on my test machine, and [Heroku][heroku.com] does something similar.  My .env file looks like:

````bash
DEBUG=1
PORT=8000
````

This allows us to change our environment  without editting the settings.py file at all!


### Dependencies
- python [I use 2.7]
    - Our application is written in Django.
- pip
    - Used as a dependency manager
- virtualenv
    - Used to install dependencies locally
- foreman
    - Used for injecting environment variables into the configuration

### Running

0. Set up a [virtual environment][http://www.virtualenv.org/en/latest/index.html#what-it-does]
    - Virtual Environment's allow you to install dependencies from requirements.txt without muddying your global environment.
    - `virtualenv venv --distribute`
    - `source venv/bin/activate` [ or windows users, see venv/bin/activate.bat]
0. `pip install -r requirements.txt`
0. `foreman run python manage.py syncdb`
0. `foreman start`

That will start gunicorn, our web server.  You could use the built-in Django one, however we like to test as close to Production as possible.
