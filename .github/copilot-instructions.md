## Operator Interaction
- When asked to fix code, first explain the problems found.
- When asked to generate tests, first explain what tests will be created.
- When making multiple changes, provide a step-by-step overview first.

## Security
- Check the code for vulnerabilities after generating.
- Avoid hardcoding sensitive information like credentials or API keys.
- Use secure coding practices and validate all inputs.

## Environment Variables
- If a .env file exists, use it for local environment variables
- Document any new environment variables in README.md
- Provide example values in .env.example

## Version Control
- Keep commits atomic and focused on single changes
- Follow conventional commit message format
- Update .gitignore for new build artifacts or dependencies

## Code Style
- Follow existing project code style and conventions
- Add type hints and docstrings for all new functions
- Include comments for complex logic

## Change Logging
- Each time you generate code, note the changes in changelog.md
- Follow semantic versioning guidelines
- Include date and description of changes

## Testing Requirements
- Include unit tests for new functionality
- Maintain minimum 80% code coverage
- Add integration tests for API endpoints

## For Python Projects Only
- Always use a Python3 virtual environment: if no venv exists, create one and activate
- Always use and update a requirements.txt file for Python modules
- Follow PEP 8 style guidelines
- Include type hints (PEP 484)

## Flask + jQuery Integration
- Use jQuery for client-side interactivity with Flask/Jinja2 templates
- Include jQuery via CDN or download locally to `static/js/` directory
- Use `$(document).ready()` to ensure DOM is loaded before executing jQuery code
- Handle AJAX requests with jQuery's `$.ajax()`, `$.get()`, or `$.post()` methods
- Use Flask's `url_for()` function in templates to generate API endpoints for AJAX calls
- Implement proper error handling for AJAX requests with `.fail()` callbacks
- Use jQuery selectors and DOM manipulation methods for dynamic content updates
- Remember to copy updated JavaScript files to `static/js/` directory after changes
- **Template Configuration**: When using organized directory structure (app/templates/, app/static/), configure Flask app with explicit paths:
  ```python
  app = Flask(__name__, template_folder='app/templates', static_folder='app/static')
  ```
- **Template Path Issues**: If encountering `jinja2.exceptions.TemplateNotFound`, verify Flask is configured with correct template_folder path
- **Static Assets**: Ensure static files (CSS, JS, images) are properly configured and accessible via Flask's static_folder setting

## Deployment and WSGI Configuration
- **Module Name Conflicts**: Avoid naming directories the same as your main Python module (e.g., don't have both `app.py` and `app/` directory)
- **WSGI Application Setup**: For Gunicorn deployment, create a proper WSGI application instance:
  ```python
  def create_app(*args, **kwargs):  # Accept optional arguments for WSGI compatibility
      # ... app configuration
      return app
  
  # Create WSGI application instance
  application = create_app()
  ```
- **Environment Variable Parsing**: Avoid inline comments in .env files that can break parsing:
  ```bash
  # BAD: Inline comments can cause parsing errors
  PAYMENT_AMOUNT=100  # Amount in cents ($1.00)
  
  # GOOD: Put comments on separate lines
  # Amount in cents ($1.00)
  PAYMENT_AMOUNT=100
  ```
- **Fly.io Configuration**: Use explicit process commands in `fly.toml` and reference the WSGI application:
  ```toml
  [processes]
  app = "gunicorn --bind 0.0.0.0:8080 --workers 2 --timeout 60 app:application"
  ```
- **Docker Build Optimization**: Use `.dockerignore` to exclude unnecessary files from build context, e.g.:
  ```ignore
  # Exclude development files, logs, and cache
  __pycache__/
  *.pyc
  .git/
  .env
  logs/
  ```
- **Docker Health Checks**: If using HTTP health checks, ensure `curl` is installed in Docker images
- **Docker User Permissions**: For non-root users in multi-stage builds: create user first, copy packages to `/home/app/.local`, set ownership with `chown -R app:app`, then switch user. Use `PATH=/home/app/.local/bin:$PATH`. "Permission denied" errors usually mean wrong ownership or PATH.
- **Cache Invalidation**: Use `flyctl deploy --no-cache` when Dockerfile changes aren't being picked up
