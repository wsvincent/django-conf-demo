# PyCon US demo for web development
Uses the official [Django polls tutorial](https://docs.djangoproject.com/en/5.2/intro/tutorial01/), but the same concepts apply to Flask and FastAPI.

## tl;dr
PyCharm is "batteries-included" just like Django. That means for almost any task you have, there is a built-in feature to save you time, you just need to know where to look. But it can feel overwhelming when starting out, so let me demo the highlights:

* Project Setup: jumpstart new projects with just a few clicks, virtual environment, Django install, boilerplate code
* IDE/Framework features: framework-specific code completion, navigation, powerful search, auto imports, refactoring
* Debugging and Testing: built-in debugger, set breakpoints, run tests
* Template Support: live previews, issues highlighted immediately, full JavaScript/TypeScript support via WebStorm
* Database: one-click connections and visualizations
* Version control: local history, Git support, visualizations, integrations with GitHub and GitLab
* Endpoints tool...

## Set up for PyCharm demo (2025.1)
Make sure you are using 2025.1.

1. Clone the repo to your local computer. From a new terminal window:
  * `$ git clone https://github.com/wsvincent/django-conf-demo.git`
2. In PyCharm:
   * Use `Run` button to start local server and check it at `http://127.0.0.1:8000/polls/`
   * There should be 5 questions there (the `db.sqlite3` database file is included in the repo; this is not a best practice, but convenient here)
   * Go to `http://127.0.0.1:8000/admin/` and login with `admin` and `testpass123` for access to the Django admin
   * In PyCharm Settings, search for "Black", install On Code Reformat & On Save (double quotes `""` are common in Django)

__Before starting demo, make sure local server is running by pressing "Run" button and have a web browser open at `http://127.0.0.1:8000/polls/`__

## Feature 1: Project Setup
* PyCharm eliminates cumbersome setup steps
* Use PyCharm + Django template in `New Project`
  * Make and set virtual env (highlight `uv` support)
  * Template language (Django/Jinja2) and project-level `templates` dir option
  * Installs Django into it
* Switch to `django-conf-demo` repo and show "Django Structure" in left sidebar. Key info you need:
  * Global `settings.py` file
  * All Admin, Models, Views in one place
  * Easy to navigate especially in larger real-world project

## Feature 2: Django Server + Templates
* Run Server with Green Run button
  * Click `http://127.0.0.1:8000/` link in Run menu on bottom (also show Red Stop and Green Run buttons in top nav)
* `Shift-Shift` to `polls.html` to open `templates/polls.html`
* Click on "Refresh to see preview" and load page
* Remove "<p>Conference demo...</p>" text and show live preview auto updates (saves time and switching windows)
* Select Terminal -> drop down arrow for `manage.py` to run `makemigrations` or `migrate`, which are part of the normal flow whenever making changes to a Django model

## Feature 3: Database Support
* At a glance visualize your entire database, tables/columns/etc
* Click `Database` icon and double-click on the `polls_question` table to show questions
* Should auto-detect but can also drag/drop `db.sqlite3` over there to establish a connection
* Double-click on `auth-user` to show full User info, too

## Feature 4: IDE Features for Django 
* Autocomplete
  * `Shift-Shift INS` to navigate to `INSTALLED_APS` in `mysite/settings.py`
  * Make a typo and show warning, ex type `newapp` at bottom of `INSTALLED_APPS` list
* Refactor
  * `Shift-Shift Index` to navigate to `polls.views.IndexView`
  * Rename `polls.html` to `index.html`, point out filename has changed, yellow warning lines immediately (Django-specific highlighting!)
* Local History
  * Right-click -> Local History -> see changes, can Revert, Create Patch, See Diff
  * Incredibly powerful, saves you if ever forget a Git commit
* Git
  * See current branch at any time at top of IDE, currently "main"
  * Click "Commit" icon in left navbar to show all changes, Select All or Just a Few
  * Click "Git icon" in bottom left to see all previous commits
  * GitHub and GitLab integrations too for easy workflow

## Feature 5: Testing & Debugging
* `Shift Shift` to `tests.py` to open `polls/tests.py`
Debugging starts with Breakpoints, markers that tell the debugger to suspend execution of the program (click gutter in line where to add or Command+F8)
* Run via Bug button or right click Debug for temporary run config




* Click the Run Gutter Icon to run just that test 

* Run server with debugger, not a big speed hit HERE!!!!!!!!!!
  * Stop server (Red Stop Sign) -> Restart with Debugger
  * Set breakpoints in:
    * `polls.views.IndexView.get_queryset`
    * Also in `polls.templates/polls/index.html`
      * Inside `{% for question in latest_question_list %}`
    * Reload the page at `/polls/`
    * Show step through Python and Django
    * Clear the breakpoints and resume

* Breakpoints and debug session...
* debug tool window
* debugger and console tabs
* step through code





## Feature 6: API Endpoints
* Click `Endpoints` icon on right navbar to open existing ones
* Note that if building out DRF or `django-ninja` API can quickly see
    https://youtu.be/xanrdSKV1k4?si=1KGl7mAjiaj7gZE2 Paul's video







### Breakpoints & Debugger
* Set a breakpoint in `views.py` for `def vote...` next to `question = ..` by click gutter for red circle
* Hit bug icon next to Green server to start in debug mode
* Run local server at polls, click through a vote
* Note info displayed in thread process



--------------------------------------------------------------------------
### Questions to Resolve...
- Endpoints: adding API too complicated?
- Frontend: worth adding dedicated JS to demo WebStorm stuff?


## Suggestions Questions for the Admin

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