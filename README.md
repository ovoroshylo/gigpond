# ![gigpond](https://user-images.githubusercontent.com/104790363/231361048-413f09c9-19b7-4ca6-b500-ba831f55fe31.png)

![gigpond_home_1](https://user-images.githubusercontent.com/104790363/231290539-64715f7f-0136-4cd8-ac5c-d79f5eb84dae.png)

## Table of contents
- [Introduction](#introduction)
- [Setup Django](#setup-django)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
- [Green Version (Default Version)](#green-version-default-version)
- [Blue Version](#blue-version)
- [Purple Version](#purple-version)
- [Light Mode](#light-mode)
- [Dark Mode](#dark-mode)
- [Set Default Home Page](#set-default-home-page)
- [manage.py Structure](#managepy-structure)
- [Tips](#tips)
- [Changelog](#changelog)

## Introduction
**Gigpond** is a simple and well-organized job listing website built-in Bootstrap version 5.1.3.
Gigpond contains lots of new designs of jobs pages with responsiveness on all screens.
I have written minimum SCSS and codes to increase performance.
This is a Python3/Django project so you have to make sure the Python installed primarily and running in your computer.

If you have any questions, feel free to email me on ovorshylo3@gmail.com
## Setup Django
Gigpond Installation in Django Python
- Python Version >> 3.8.10
- Django Version >> 3.2.7
- Bootstrap Version >> 5.1.1

### Prerequisites
Please follow below steps to install and setup all prerequisites:

  #### - Nodejs
  Make sure the version of `Node.js` is greater than 14**. Use the `LTS` Version for the Node Js.

  #### - Yarn
  Make sure to have the `Yarn` installed & running in your computer. We recommend `Yarn` instead of `NPM`.

  #### - Gulp 
  Make sure you have `Gulp` installed & running on your computer. If you already installed gulp, run command `npm install -g gulp` from your terminal.

  #### - Git 
  You must have `Git` installed & running on your PC. Installation For setting up the Landing theme, follow the below process.

  #### - Python
  If you already have installed `Python` on your computer, you can skip this step. Please use Python version 3 or if you are using Python version 2 then make sure to run all the below commands with python insted of python3.

  ##### For windows
  * Download python from windows store.
  * Select the Python's version to download.
  * Click on the Install Now.
  * Installation in Process

  ##### For Linux
  * sudo apt update
  * sudo apt install python3

  #### - Check Pip version
  ```
  py -m pip --version
  upgrade pip
  py -m pip install --upgrade pip
  ```

  #### - Virtualenv
  Make sure to have the `virtualenv` installed globally & running on your computer. If you already have installed on your computer, you can skip this step.

  ##### Virtualenv installation command for linux & mac os
  `python3 -m pip install --user virtualenv`

  ##### Virtualenv installation command for Windows
  `py -m pip install --user virtualenv`

### Installation
To setup the Landing theme, follow below-mentioned steps:

#### - Install Prerequisites
Make sure to have all above prerequisites installed & running on your computer

After you finished with the above steps, you can run the following commands into the terminal / command prompt from the root directory of the project to run the project locally or build for production use:

Command | Description
:--- | :---
<span style="color: red">*python3 -m venv env_name*</span> | Create Virtual Environment & on Linux & mac OS
python -m venv env_name	| Create Virtual Environment on Windows OS
source environment_name/bin/activate | Activate Environment on Linux & mac OS
environment_name\Scripts\activate	| Activate Environment on Windows OS
pip3 install django	| Install Django on Linux & mac OS
pip install Django | Install Django on Windows OS

`Note: `Depending on your installation, you may need to use either pip3 or pip and for python you may need to use either python3 or python.

After you finished with the above steps, you can run the following commands into the terminal / command prompt from the root directory of the project to run the project locally:

#### - Database Connectivity
Go to `settings.py` of `gigpond` directory and update below settings.

```
DATABASES = {
    'default': {
    'ENGINE': 'django.db.backends.#databaseservername#',
    'NAME': 'Your Database Name',
    'USER' : 'Database User Name',
    'PASSWORD' : 'Your Password',
    'HOST' : 'Write down Host',
    'PORT' : 'Write down port',
    }
}
```

#### - Run below command for database migration
For Windows: `python manage.py migrate`<br>
For Linux: `python3 manage.py migrate`

#### - To create a superuser run the below command
`python manage.py createsuperuser`
enter username Your Username
enter your Email Address
enter your Password
enter your Password again

#### - `Note:` After open terminal and enter command `gulp`

#### - Run below command for run your project
For Windows: `python manage.py runserver`
For Linux: `python3 manage.py runserver`

#### - To load static files
Go to `gigpond/setings.py` and add following command:-
```
STATIC_URL = '/static/'
STATICFILES_DIRS = [os.path.join(BASE_DIR,'static')]
STATIC_ROOT= os.path.join(BASE_DIR,'assets')
python manage.py collectstatic
```

#### - SMTP CONFIGURATION
Go to `gigpond/settings.py` and update credential
```
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = 'YOUR EMAIL ADDRESS'
EMAIL_HOST_PASSWORD = 'YOUR HOST Password'
DEFAULT_FROM_EMAIL = 'YOUR EMAIL ADDRESS'
```

## Green Version (Default Version)
![gigpond_green](https://user-images.githubusercontent.com/104790363/231354979-6a0c61df-139d-4e49-9736-93f2b00625c7.png)

The green color version is a default version set by `color="green"` at line number 31 in the `src/js/pages/switcher.init.js.`

## Blue Version
![gigpond_blue](https://user-images.githubusercontent.com/104790363/231355411-fb9ce096-5621-43ac-9ffe-707ac36a9442.png)

The Blue color set by `color="blue"` at line number 31 in the `src/js/pages/switcher.init.js.`

## Purple Version
![gigpond_purple](https://user-images.githubusercontent.com/104790363/231355488-423f3b4f-97c5-47ed-8bd5-16611884dbfc.png)

The Purple color set by `color="purple"` at line number 31 in the `src/js/pages/switcher.init.js.`

## Light Mode
![gigpond_light](https://user-images.githubusercontent.com/104790363/231355795-4648712e-f188-443b-8661-0e5ed7e0e61c.png)

The Light color set by `var mode = 'light'` at line number 49 in the `src/js/pages/switcher.init.js.`

## Dark Mode
![gigpond_dark](https://user-images.githubusercontent.com/104790363/231355865-fae2e287-9e3a-4623-b674-db271d629401.png)

The Dark color set by `var mode = 'dark'` at line number 49 in the `src/js/pages/switcher.init.js.`

## Set Default Home Page
#### - Index 1
Go to `gigpond/urls.py.`
and update code `path('', views.Index.as_view(),name='index')` at line number 24.

#### - Index 2
Go to `gigpond/urls.py.`
and update code `path('', views.Index2.as_view(),name='index')` at line number 24.

#### - Index 3
Go to `gigpond/urls.py.`
and update code `path('', views.Index3.as_view(),name='index')` at line number 24.

## manage.py Structure
```
  #!/usr/bin/env python
    """Django's command-line utility for Landingistrative tasks."""
    import os
    import sys
    
    def main():
        """Run Landingistrative tasks."""
        os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'xegal.settings')
        try:
            from django.core.management import execute_from_command_line
        except ImportError as exc:
            raise ImportError(
                "Couldn't import Django. Are you sure it's installed and "
                "available on your PYTHONPATH environment variable? Did you "
                "forget to activate a virtual environment?"
            ) from exc
        execute_from_command_line(sys.argv)
    
    
    if __name__ == '__main__':
        main()
  ```

## Tips
`SCSS:` I suggest you not to do any changes in any scss files from `src/scss/custom` folders because it will trouble in future updates so I am suggesting that if you want to make any changes you can create a new `custom.scss` file and use that instead of the theme's file. If you have any questions beyond this documentation, feel free to contact us at ovorshylo3@gmail.com

## Changelog
`v1.0.0` - 25 April 2022
- Initial released