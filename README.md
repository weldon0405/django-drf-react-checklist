# django-drf-react-checklist
A checklist for getting a Django / REST Framework and React project off the ground.

- [ ] 1. Create directory 
    ```bash
    mkdir <dir_name>
    ```

- [ ] 2. Create virtual environment and install django and drf
    ```bash
    pipenv install django djangorestframework
    ```

- [ ] 3. Install dev dependencies **
    ```bash
    pipenv install pylint coverage --dev
    ```

- [ ] 4. Check for test coverage periodically during development
   ```bash
   coverage run --source='.' manage.py test
   ```
   Check test coverage and output in html file
    ```bash
    coverage html
    ```
    Check test coverage and output in terminal
    ```bash
    coverage report
    ```

- [ ] 5. Add `rest_framework` and other apps to the project's `settings.py`
    ```python
    INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'rest_framework',
    'frontend',
    'users_api',
    ]
    ```

- [ ] 6. Create model(s) in 'models.py'
    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```

- [ ] 7. Build API views >> generic API views, class-based views, or function-based views

- [ ] 8. Build urls
    Include app urls in project's urls.py
    Create app's urls.py, e.g., 'api/users/'

- [ ] 9. Check via `python manage.py runserver` >> localhost:8000

- [ ] 10. Create a few db records via API view POST form

- [ ] 11. *** Skipped creation of additional fake data during tutorial

- [ ] 12. create the frontend app and build folder structure
    ```bash
    mkdir <project>/frontend/src/components
    mkdir <project>/frontend/src/{static,templates}/frontend
    ```

- [ ] 13. Create the package.json   *** -y  utilizes default settings
    ```bash
    npm init -y
    ```

- [ ] 14. Install babel for transpiling the JS
    ```bash
    npm i babel-core babel-loader babel-preset-env babel-preset-react --save-dev
    npm i babel-preset-stage-2 babel-plugin-transform-class-properties --save-dev
    ```

- [ ] 15. Create '.babelrc' and input config, e.g,
    ```javascript
		{
		    "presets": [
			"env",
			"react",
			"stage-2"
		    ],
		    "plugins": [
			"transform-class-properties"
		    ]
		}
    ```

- [ ] 16. Create webpack.config.js for webpack configuration, example:
    ```javascript
		module.exports = {
		    module: {
		      rules: [
			{
			  test: /\.js$/,
			  exclude: /node_modules/,
			  use: {
			    loader: "babel-loader"
			  }
			}
		      ]
		    }
		  };
      ```

- [ ] 17. Create index.html    *** React's entrypoint into the app
    ```javascript
    <div id="app"><!-- React --></div>
    ```    

- [ ] 18. Modify 'frontend/views.py' to create an index view
    ```python
    def index(request):
		  return render(request, 'frontend/index.html')
    ```

- [ ] 19. Configure the new URL mapping to include the frontend in <project>/urls.py
  
    ```python
    urlpatterns = [
		    path('admin/', admin.site.urls),
		    ...,
		    path('', include('frontend.urls')),
		]
    ```
  
- [ ] 20. Create 'frontend/urls.py' and wire up the route
		urlpatterns = [
		    path('', views.index),
		]

- [ ] 21. Add frontend to INSTALLED_APPS in  <project>/settings.py

- [ ] 22. Create 'frontend/src/components/app.js'  *** This is the main component for attaching React to <div id='app'></div>

- [ ] 23. Install React, ReactDOM, and prop-types
    ```bash
    npm i react react-dom prop-types --save-dev
    ```

- [ ] 24. Create entry point 'frontend/src/index.js'
    ```javascript
    import App from './src/index';
    ```
