# PyCon US demo for web development
Uses the official [Django polls tutorial](https://docs.djangoproject.com/en/5.2/intro/tutorial01/), but the same concepts apply to Flask and FastAPI.

## tl;dr
PyCharm is "batteries-included" just like Django. That means for almost any task you have, there is a built-in feature to save you time, you just need to know where to look. But it can feel overwhelming when starting out, so let me demo the highlights:

* Fast Project Setup
* IDE & Framework-specific features
* Debugging & Testing
* Template Support
* Database integration and visualization
* Advanced Version Control
* API Endpoints tool and more

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
   * In PyCharm Settings, search for "Black" under `Tools`, install On Code Reformat & On Save (double quotes `""` are common in Django)

__Before starting demo, make sure local server is running by pressing "Run" button and have a web browser open at `http://127.0.0.1:8000/polls/`__

## Feature 1: Project Setup
* PyCharm eliminates cumbersome setup steps
* Use PyCharm + Django template in `New Project`
  * Make and set virtual env (highlight `uv` support)
  * Template language (Django/Jinja2) and project-level `templates` dir option
  * Installs Django into it
* Switch to `django-conf-demo` repo and show "Django Structure" in left sidebar. The key info you need is quickly visible:
  * Global `settings.py` file
  * All Admin, Models, Views in one place
  * Easy to navigate especially in larger real-world project

## Feature 2: Django Server + Templates
* `Shift-Shift` to `polls.html` to open `templates/polls.html`
* Click on "Run django-conf-demo" to start server and see the page
  * Depending on the visitor, can be fun to go through these questions, demo the Polls tutorial if they're not already familiar
* Remove "<p>Conference demo...</p>" text and show live preview auto updates (saves time and switching windows)

## Feature 3: Database Support
* At a glance visualize your entire database, tables/columns/etc
* Click `Database` icon --> `db` --> `main` --> double-click on the `polls_question` table to show questions. Also double-click on `polls_choice` to show responses. And `auth-user` to show full User info.
* Note that can see this info in built-in admin, but quick view within IDE to not breakup your flow
* Should auto-detect but can also drag/drop `db.sqlite3` over there to establish a connection

## Feature 4: IDE Features for Django 
* Autocomplete
  * `Shift-Shift INST` to navigate to `INSTALLED_APS` in `mysite/settings.py`
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
* Basic Testing:
  * `Shift Shift` to `tests.py` to open `polls/tests.py`
  * Run all tests quickly by selecting "Current File" at top and click `RUN` button 
  * Click the gutter icon to run just that test for `class QuestionModelTests(TestCase)`
* Coverage Support:
  * In top nav, click the 3 dots to the right of Debugger and select "Run Tests with Coverage". Will install Coverage if not already.
  * Run tests with coverage --> see report. If go to `polls/views.py` areas NOT covered will be in red vs green if covered by tests
* Debugger:
  * PyCharm has a powerful built-in debugger where we can set Breakpoints to suspend execution of a program and dive in 
  * Go to `polls/views.py` and set a gutter breakpoint within `IndexView` at `return Question.objects.filter`
    * Start the Debugger via the Bug icon in top nav
    * Refresh the page at `http://127.0.0.1:8000/polls/` and then view Debug in bottom console, note "Threads and Variables" to view full debug information about the code (in this case, works as expected)
  * Clear the breakpoint in `polls/views.py` and resume

## Feature 6: API Endpoints
* Open `polls/urls.py` file and click "Endpoints" icon in right navbar
  * Shows existing endpoints, HTTP methods, related file
* If building out APIs with Django REST Framework or `django-ninja` can quickly see
    https://youtu.be/xanrdSKV1k4?si=1KGl7mAjiaj7gZE2 Paul's video

----------------------------------------------------------  
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