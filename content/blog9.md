Title: Virtual Environment 
Date: 2017-02-08 10:20
Category: Review

Working on my Capstone project for the Data Science Immersive program at GA, I required to work with timeseries. Specifically, I needed to work with a library that was only available on a development version of statsmodel package. One thing I could do was to download the development version of statsmodel from github and set it up by running the setup.py to replace the current official statmodel version. However, this could mess up all the tested and working libraries and I did not want to risk that. So, instead I decided to make a virtual environment and set the version of python and libraries I needed in that environment without any interference with outside of that environment. To create a virtual environment follow these simple steps:
Install virtualenv using pip:
``` python
pip install virtualenv
```
Create a virtual environment for this specific project you are working on:

``` python
cd project_folder
virtualenv venv
``` 
virtualenv venv creates a folder in the current directory which will contain the Python executable files, and a copy of the pip library which you can use to install other packages. The name of the environment (venv in this case) can be anything.
This creates a copy of Python in the folder that you created for virtual environment. You can also use your version of choice for Python (like python 2.7).
``` python
virtualenv -p /usr/bin/python2.7 venv
```
To activate the virtual environment, try:
``` python
source venv/bin/activate
```
and when done working with it type:
``` python
deactivate
```
In order to install packages you can use:
``` python
pip install requests
```
Also note running virtualenv with the option --no-site-packages will not include the packages that are installed globally which gives you the flexibility to use your required version of packages.

