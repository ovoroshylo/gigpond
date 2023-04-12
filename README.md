# Gigpond

![gigpond_home_1](https://user-images.githubusercontent.com/104790363/231290539-64715f7f-0136-4cd8-ac5c-d79f5eb84dae.png)

## Table of contents
- [Introduction](#Introduction)
- [Setup Django](#Setup Django)
  * [Prerequisites](#Prerequisites)
  * [Simulator CLI](#simulator-cli)
  * [Other utilities](#other-utilities)
- [Language services and Tests](#language-services-and-tests)

## Introduction
Gigpond is a simple and well-organized job listing website built-in Bootstrap version 5.1.3.
Gigpond contains lots of new designs of jobs pages with responsiveness on all screens.
I have written minimum SCSS and codes to increase performance.
This is a Python3/Django project so you have to make sure the Python installed primarily and running in your computer.

If you have any questions, feel free to email me on ovorshylo3@gmail.com
## Setup Django
### Prerequuisites
Please follow below steps to install and setup all prerequisites:

  - Nodejs
    Make sure the version of **Node.js is greater than 14**. Use the **LTS**`** Version for the Node Js.

  - Yarn
    Make sure to have the **Yarn** installed & running in your computer. We recommend **Yarn** instead of **NPM**.

  - Gulp     
    Make sure you have Gulp installed & running on your computer. If you already installed gulp, run command **npm install -g gulp** from your terminal.

  - Git
    You must have **Git** installed & running on your PC. Installation For setting up the Landing theme, follow the below process.

  - Python
     If you already have installed **Python** on your computer, you can skip this step. Please use Python version 3 or if you are using Python version 2 then make sure to run all the below commands with python insted of python3.

      **For windows**
        * Download python from windows store.
        * Select the Python's version to download.
        * Click on the Install Now.
        * Installation in Process
      **For Linux**
        * sudo apt update
        * sudo apt install python3

  - Check Pip version
    * py -m pip --version
    * upgrade pip
    * py -m pip install --upgrade pip

### Git
  Make sure to have the git installed globally & running in your computer





Gigpond Installation in Django Python
  - Python Version >> 3.8.10
  - Django Version >> 3.2.7
  - Bootstrap Version >> 5.1.1

## Installation Python
 - https://www.python.org/downloads/
### For Windows OS 
 - Download python  from windows store
 - Select the Python's version to download.
 - Click on the Install Now
 - Installation in Process
### For Linux OS
 - sudo apt update
 - sudo apt install python3

> Note: Depending on your installation, you may need to use either pip3 or pip and for python you may need to use either python3 or python.

> Open terminal
  python --version
 
> To check pip version  
  1. py -m pip --version
  2. upgread pip 
  3. py -m pip install --upgrade pip

## Installing virtualenv   
  - linux & mac os
    python3 -m pip install --user virtualenv

  - Windows
    py -m pip install --user virtualenv

### Create Virtual Environment
  - linux & mac os
    python3 -m venv environment_name

  - Windows
    python -m venv environment_name

### Activate Environment
  - Linux & mac os
    source environment_name/bin/activate
  - Windows
    environment_name\Scripts\activate
 
## Install Django
  - linux & mac os
    pip3 install django

  - Windows
    pip install django
 
### First please check Django properly Installed or not
 - Linux/macOS
  python3 -m django --version

 - Windows
  python  -m django --version

## Other requirements
  Goto project directory using cd command



## Configurations
  Goto gigpond/settings.py of Main Directory

  - DATABASE CONFIGURATION
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.#databaseservername#',
            'NAME': 'Your Database Name',
            'USER' : 'Database User Name',
            'PASSWORD' : 'Your Password',
            'HOST' : "Write down Host",
            'PORT' : 'Write down port',
        }
    }

  - SMTP CONFIGURATION
    EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
    EMAIL_HOST = 'smtp.gmail.com'
    EMAIL_PORT = 587
    EMAIL_USE_TLS = True
    EMAIL_HOST_USER = 'YOUR EMAIL ADDRESS'
    EMAIL_HOST_PASSWORD = 'YOUR HOST Password'
    DEFAULT_FROM_EMAIL = 'YOUR EMAIL ADDRESS'
    SERVER_EMAIL = 'YOUR EMAIL ADDRESS'

  - Add following command:
    STATIC_URL = '/static/'
    STATICFILES_DIRS = [os.path.join(BASE_DIR,'static')]

  - Run Command In Terminal
    > python manage.py collectstatic
    > Goto settings.py of Main Directory

#######To Set Default Color#########
Goto src/js/pages/switcher.init.js
<!--===========================================================================-->
                        <!--Color Mode -->
<!--===========================================================================-->
## Make changes according choice at Line No 29
1. Green 
color = "green"
2. Blue
color = "blue"
3. Purple 
color = "purple"

<!--===========================================================================-->
>> To set Default light/dark/RTL Mode
<!--===========================================================================-->
Go src/js/pages/switcher.init.js
-line number 47
<!--===========================================================================-->
> For Light theme
var mode = 'light'
> For Dark theme
var mode = 'dark'
<!--===========================================================================-->
<!--===========================================================================-->

###########To Set Default home page ############

follow this steps:
Goto  gigpond/urls.py
At line number 24 use following line 

> for index 1
path('', views.Index.as_view(),name='index'),

> for index 2
path('', views.Index2.as_view(),name='index'),

> for index 3
path('', views.Index3.as_view(),name='index'),

-> Windows:-python manage.py migrate
-> Linux:-python3 manage.py migrate

## Run your project
- Windows:-python manage.py runserver
- Linux:-python3 manage.py runserver
