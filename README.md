# django-single-folder-project-template

This is a Django project template for use with `django-admin startproject`.

It implements the _single project and app folder_ layout described by,
among others, [softwarecrafts.uk](https://softwarecrafts.uk/100-words/day-91) [(wayback)](https://web.archive.org/web/20240722181831/https://softwarecrafts.uk/100-words/day-91) and 
[noumenal.es](https://noumenal.es/notes/django/single-folder-layout/) [(wayback)](https://web.archive.org/web/20240722181955/https://noumenal.es/notes/django/single-folder-layout/).

## Usage

`django-admin startproject --template=https://github.com/Kagee/django-single-folder-project-template/archive/refs/heads/main.zip project_name .`

This wil make a Django project name `project_name` in the current folder. 

We setup the project in the current folder so we do not make two levels of folders name `project_name`.

## How?

The project folder template is a combination of the [upstream](https://github.com/django/django/tree/main/django/conf) `project_template` and `app_template` folders. 

In addition to this, the template will

* Add itself as a [installed app](project_name/settings.py-tpl#L40) in `INSTALLED_APPS`
* Configures a [template directory](project_name/settings.py-tpl#L59) in `project_name/templates` using `TEMPLATES.DIRS`
* Configures a [static folder](project_name/settings.py-tpl#L123) in `project_name/static` using `STATICFILES_DIRS`

## Why?

This is a template for a project using Django where, I quote 
> ... building a single Django app is too much boilerplate. 

It is useful for very simple prototypes or demos, or where you are 
sure that your app will not be re-used in another Django project.

## LICENSE

Since this is pretty much just a minor modification of the default Django
project and app templates, it has the same license as Django, see LICENSE.
