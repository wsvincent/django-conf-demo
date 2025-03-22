# Django Tutorial Extended 2025
[Django polls tutorial](https://docs.djangoproject.com/en/5.2/intro/tutorial01/) extended for PyCharm demos.

PyCharm is "batteries-included" just like Django.
- Jump-start a new project in a few clicks (virtual envs, dependencies, boilerplate code)
- Django-specific code insights, code completion, and debugging help
- Template support and live previews; full TypeScript & JavaScript support via WebStorm
- Database connections in one click and visualizations
- Git support, visualizations, and integration
- AI Assistant specific to Django to save time and generate insights

## Installation
- Clone this repo and open PyCharm Professional, which should:
  - Make a virtual environment
  - Prompt to install dependencies from `requirements.txt`
  - Configure the settings that recognize this as a Django project
- Setup the local database
  - Open `Tools | Run manage.py task` to open PyCharm's `manage.py` console
    - `migrate` to configure initial database
    - `createsuperuser` (and answer questions) to create superuser account to access admin (`admin`, `admin@email.com`, `testpass123` are good defaults)
- Run local server
  - Open `http://127.0.0.1:8000/admin/` and add a question (see bottom for suggestions!)
  - Click the Run Green Arrow to start and visit `http://127.0.0.1:8000/polls/`
  - In separate browser tab, 
- Add Black
  - Go to PyCharm Settings, search for "Black", install On Code Reformat & On Save

## Features

### Databases
- Super lazy & visual way to explore databases
- Click database icon -> drag & drop `db.sqlite3` into it to make the connection
- At a glance see everything, tables/columns






## Junie
- write tests for me

## AI Assistant



### Explore Project
- Templates live loading
- Database visuals
- Autocomplete
- Endpoints?
- Frontend support?
- Version Control


### Templates
- Visual live view
- Write template name in view, create from there. 
- PyCharm detect template files with autocomplete










### 2. Running Django Server




Templates


Database


Endpoints

Frontend Support


### Version Control
* Local History
  * Right-click -> Local History -> see changes, can Revert, Create Patch, See Diff
* Git
  * Installed already via start-up panel. 
  * New project files are RED because not added to Git. Right-click -> Git -> + Add. File now GREEN and added.
  * Click Git sidebar, double-click changes to see visual differences
  * Bottom section, click Git icon to see all previous commits on current branch
* GitHub, GitLab, etc integrations


### IDE Features for Django
* Autocomplete


## Suggestions Questions

1. What is the current version of Django?
   * 5.1
   * 5.2
   * 6.0

2. Django was initially developed at which organization?
  * NASA
  * Instagram
  * A newspaper

3. Which of these is not a built-in Django management command?
   * `makemigrations`
   * `makemagic`
   * `migrate`

4. What is Django's default database engine?
  * PostgreSQL
  * SQLite
  * MySQL 

5. What's the default port when running `python manage.py runserver`?
  * 80
  * 8080
  * 8000