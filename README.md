# PyCon US demo for web development
Uses the official [Django polls tutorial](https://docs.djangoproject.com/en/5.2/intro/tutorial01/), but the same concepts apply to Flask and FastAPI.

## tl;dr
PyCharm is "batteries-included" just like Django. That means for almost any task you have, there is a built-in feature to save you time. Here are the highlights of what I'll demo for you:

* Project Setup
* Live Templates 
* Database Tool Window
* Code Completion
* Testing and Debugging 

## Set up for PyCharm demo (2025.1)
Make sure you are using 2025.1.

1. Clone the repo to your local computer. From a new terminal window:
   * `$ git clone https://github.com/wsvincent/django-conf-demo.git`
2. In PyCharm:
   * Use the `Run` button to start the local server and check it out at `http://127.0.0.1:8000/`
   * There should be 5 questions there (the `db.sqlite3` database file is included in the repo; this is not a best practice, but convenient here)
   * Go to `http://127.0.0.1:8000/admin/` and login with `admin` and `testpass123` for access to the Django admin
   * In PyCharm Settings, search for "Black" under `Tools`, install On Code Reformat & On Save (double quotes, `""`, are common in Django)

__Before starting demo, make sure local server is running by pressing "Run" button and have  a web browser open at `http://127.0.0.1:8000/`__

## Feature 1: Project Setup
In this part of the demo we will be showing:
* How PyCharm allows for fast Django/Flask/FastAPI project setup
* Django Structure Tool window for quick navigation

### Why is this important?
* Project setup is very complicated for web development, but with PyCharm you can do it all within the IDE. * With PyCharm, there's no need to use Terminal to navigate to your preferred location, configure a virtual environment, install Django, and so on.
* PyCharm also makes it easy to see a top-level view of your project with the Django Structure Tool window.
* Navigating around a real-world project is time-consuming, but PyCharm makes it easy to do.

### Steps in demo
* In PyCharm -> File -> New Project and select "Django"
* The new project configuration will be displayed. Explain how there are options for Python interpreter type (including `uv`), location, Git integration, even advanced options around templating, project name, and more.
* Switch to the already-open `pycon-us-demo` repo and show the "Django Structure" on the left sidebar. It has the key info you need:
  * Global `settings.py` file
  * Admin, Models, and Views in one place

### Key Takeaway
* Project setup and navigation is a big hurdle in web development. PyCharm makes it easy for us.

## Feature 2: Live Templates
In this part of the demo we will be showing:
* Live Templates allow for visual changes to the codebase within the IDE
* There is no need to toggle between the IDE and a web browser
* PyCharm `Run` button makes starting and stopping the local web server easy

### Why is this important?
* Without this feature, web developers must constantly toggle between their IDE and a web browser to view code changes. 
* Starting and stopping the local web server is a big pain requiring usage of the Terminal. PyCharm has a simple visual way to do this. (And a powerful debugger option, which we'll get to shortly).

### Steps in demo
* Type `Shift-Shift` to open Search Everywhere feature and type `polls.html` to open the  `templates/polls.html` template file.
* PyCharm will open the file and a side window with live preview. Click on "Run Django" to start the local server and see the page (it's `polls/` if you must specify the URL).
* Ask at least one of the questions to the visitor and show how you can select the question, select a response, and then navigate back to the main Polls page all within the IDE. (Correct answers are at the bottom of this Readme.)
* Demonstrate live updates by going to the `polls.html` file and remove the `<p>Conference demo...</p>` text from the `polls.html` file. Show how live preview auto updates. This saves time and removes the need to switch windows constantly. 
* Use `Ctrl+z` to add the text back before continuing on so you can reuse it for the next demo.

## Feature 3: Database Tool Window
In this part of the demo, we will be showing:
* How PyCharm allows you to view the contents of a local or remote database without leaving the IDE

### Why is this important?
* Web developers often work with production databases like PostgreSQL that require their own server and port.
* Even more complicated setup if a remote server on AWS, Digital Ocean, etc.
* PyCharm brings all this complexity into a single graphical interface

### Steps in demo
* Type `Shift-Shift` to open Search Everywhere and type `models` to open `models.py` file with our database information.
* Click on the Database tool window on the far right of PyCharm.
* An introspected database will appear. Explain how you can see all parts of the database, down to the schema of specific tables, so you know exactly what is in there.
* Double-click on the `polls_question` table to show the polls questions we just saw on the website.
* Can also double-clik on `polls_choice` to show responses.
* Note that you can see this info in the Django admin _if_ you configure it properly, but much easier to have visual way within the IDE to do so.

## Feature 4: Code Completion
In this part of the demo, we will be showing:
* How PyCharm's local code completion makes coding easier
* Our in-house machine learning team have developed smart code completion that supports frameworks like Django
* This is fast and targeted code completion, separate from our offerings for AI Assistant and Junie that work with 3rd party models from ChatGPT, Claude, Gemini, or local LLM of your choice.

### Why is this important?
* Code completion is an important productivity feature for web developers.
* Many (if not most) web developers use code completion now. It's important to mention how powerful our out-of-the-box option is while _also_ having AI Assistant and Junie if needed.

### Steps in demo
* Navigate to `polls/models.py` file, either with Search Everywhere or by clicking tab on left sidebar
* At the bottom of the file, below `class Choice(models.Model):` add a new class for a Comment model, meaning users can add comments on the poll.
* Start typing `class Comment`... code completion will quickly autosuggest something like:

```python
class Comment(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    comment_text = models.CharField(max_length=200)
```

* This code option works, it is a basic model for a Comment that has a Foreign Key relationship to the `Question` model and a field for `comment_text`.
* Can note that to fully add this feature would need to add a related `views.py` file, template file, and update `polls/urls.py` to display it.
* The point is not that code completion writes all your code for you, but rather that PyCharm is smart enough to guess common use cases and save you from typing.

## Feature 5: Testing & Debugging
In this part of the demo, we will be showing:
* How PyCharm supports testing and coverage all within the IDE

### Why is this important?
* Professional web developers spend a large amount of time writing and running tests.
* PyCharm's support speeds up this process immensely.
* PyCharm's debugger has long been a killer feature that enables zooming in on any code issues.

### Steps in demo
* Type `Shift Shift` and type `tests.py` to open the `polls/tests.py` file.
* You can quickly run all tests. In the top navbar next to the Run arrow, select "Current File" and then click `Run` button to run the tests. The Terminal window will show up at the bottom with info on 10 tests passing.
* Or run specific tests. Click the Run arrow in the gutter next to `class QuestionModelTests(TestCase):` to run just that test class, which shows 3 tests.
* There is support for Coverage, a code coverage tool widely used in Python.
* In the top nav, click the 3 dots to the right of the Debugger and select "Run Tests with Coverage." It will install Coverage if not already installed. This generates a report, `polls.tests`, that you can see. Notice that `views.py` only has 72% coverage.
* Navigate to `polls/views.py` and areas NOT covered will be in red vs green if covered by tests.

## Feature 6: Debugger
In this part of the demo, we will be showing:
* PyCharm's built-in debugger to help step through code quickly
* One of PyCharm's original killer features that long-time users love

### Why is this important?
* Professional web developers often have to debug code they (or someone else) wrote.
* Existing tools are either basic like `print` statements or use `breakpoint()` but PyCharm has a powerful visual suite of debugging tools.
* With PyCharm's debugger we can set breakpoints, inspect variables, and step through the code visually.

### Steps in demo
* Navigate to `polls.html` tab already open. Set a Breakpoint inside `{% for question in latest_question_list %}` by clicking in the Gutter so a Red Circle appears.
* Stop the running server. Restart it with the Debugger Icon. Normally need to refresh web page but since in Live Template, done automatically.
* Within the Debugger tab, can see on the left the "Stack Frames" that represent the current state of the program. The Variables panel has variables at that execution point in the right tab.
* Emphasize that can step through the code line by line as needed without needing `print` or `breakpoint()` statements.
* Clear the breakpoint and resume.

## Conclusion
* This is just a taste of PyCharm's support for Django. PyCharm makes your existing workflow faster and easier to use, all within the IDE.

----------------------------------------------------------  
## Suggestions Questions for the Admin

1. What is the current version of Django?
   * 5.1
   * 5.2 (answer)
   * 6.0

2. Django was initially developed at which organization?
  * NASA
  * Instagram
  * A newspaper (answer)

3. Which of these is not a built-in Django management command?
   * `makemigrations`
   * `makemagic` (answer)
   * `migrate`

4. What is Django's default database engine?
  * PostgreSQL
  * SQLite (answer)
  * MySQL 

5. What's the default port when running `python manage.py runserver`?
  * 80
  * 8080
  * 8000 (answer)