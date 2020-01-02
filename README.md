# Django Dev

### Useful Commands

`docker-compose run web python manage.py <insert here>`:

- `startapp <name of app>` = Creates a new app (polls)
- `startproject <name of project>` = Creates a new project (app)
- `createsuperuser` = Prompts to create a super user
- `migrate` = Run a migration
- `makemigrations` = Create migrations
- `sqlmigrate <app name> <migration file number>` = Show raw SQL the migration is running (Example: `sqlmigrate polls 0001`)
- `check` = Check for any common problems
- `test` = Run tests

### Projects vs Apps [(Cite)](https://docs.djangoproject.com/en/3.0/intro/tutorial01/#creating-the-polls-app)

"An app is a Web application that does something – e.g., a Weblog system, a database of public records or a small poll app. A project is a collection of configuration and apps for a particular website. A project can contain multiple apps. An app can be in multiple projects"

### FAQ

**App is broken after changing `app/settings.py` (update database, etc)**

- Run `docker-compose build` to rebuild the containers with the updated value(s)

**App throwing errors on Models**

- Run `docker-compose run web python manage.py migrate` (Might be attempting to access tables that do not yet exist)