![Laravel GitScrum](http://i.imgur.com/fJLrnxu.png)

<p align="center">
<b><a href="#overview">Overview</a></b>
|
<b><a href="#installation">Installation</a></b>
|
<b><a href="#setup">Setup</a></b>
|
<b><a href="#screens">Screens</a></b>
|
<b><a href="#questions-and-issues">Questions and Issues</a></b>
|
<b><a href="#contributing">Contributing</a></b>
|
<b><a href="#license">License</a></b>
</p>

<hr>

[![Laravel 5.4](https://img.shields.io/badge/Laravel-5.4-brightgreen.svg?style=flat-square)](http://laravel.com)
[![Build Status](https://travis-ci.org/renatomarinho/laravel-gitscrum.svg?branch=master)](https://travis-ci.org/renatomarinho/laravel-gitscrum)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/2abfe5173e0b4565a2b1e3e345160939)](https://www.codacy.com/app/renatomarinho/laravel-gitscrum?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=renatomarinho/laravel-gitscrum&amp;utm_campaign=Badge_Grade)
[![Total Downloads](https://poser.pugx.org/renatomarinho/laravel-gitscrum/downloads)](https://packagist.org/packages/renatomarinho/laravel-gitscrum)
[![License](http://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/renatomarinho/laravel-gitscrum/blob/master/LICENSE.md)
[![OpenCollective](https://opencollective.com/laravel-gitscrum/backers/badge.svg)](#backers) 
[![OpenCollective](https://opencollective.com/laravel-gitscrum/sponsors/badge.svg)](#sponsors)

<hr>

## Overview

Laravel GitScrum is a **free application** developed in Laravel 5.4. The aim is help the developer teams to use **Git** and **Scrum** on task management of the day-to-day.

Available in English, Chinese, Russian, German, Spanish, Portuguese, Italian, French, Indonesian and Hungarian.


Laravel GitScrum in gitter.im : [https://gitter.im/laravel-gitscrum/Lobby](https://gitter.im/laravel-gitscrum/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)

### Features

GitScrum can be integrated with **Github** or **Gitlab**.

- **Product Backlog** contains the Product Owner's assessment of business value

- **User Story** is a description consisting of one or more sentences in the everyday or business language that captures what a user does or needs to do as part of his or her job function.

	**Features**: Acceptance criteria, prioritization using MoSCoW, definition of done checklist, pie chart, assign labels, team members, activities, comments and issues.

- **Sprint Backlog** is the property of the development team and all included estimates are provided by development team. Often an accompanying sprint planning is the board used to see and change state of the issues.

	**Features**: Sprint planning using Kanban board, burndown chart, definition done checklist, effort, attachments, activities, comments and issues.

- **Issue** is added in user story to one sprint backlog, or directly in sprint backlog. Generally, each issue should be small enough to be easily completed within a single day.

	**Features**: Progress state (e.g. to do, in progress, done or archived), issue type (e.g. Improvement, Support Request, Feedback, Customer Problem, UX, Infrastructure, Testing Task, etc...), definition of done checklist, assign labels, effort, attachments, comments, activities, team members.



## Installation

The requirements to Laravel GitScrum application is:

- **PHP - Supported Versions**: >= 7.x
- **Webserver**: Nginx or Apache
- **Database**: MySQL, or Maria DB

[**Use Docker** - Containers: php7, nginx and mysql57](https://github.com/renatomarinho/Docker-GitScrum)

### Composer Package

```
$ composer create-project renatomarinho/laravel-gitscrum --stability=stable --keep-vcs
$ cd laravel-gitscrum
```
**Important**: If you have not yet installed composer: [Installation - Linux / Unix / OSX](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)


### Git Clone

```
$ git clone git@github.com:renatomarinho/laravel-gitscrum.git
$ cd laravel-gitscrum
$ composer update
$ composer run-script post-root-package-install
```


## Setup

**Important**: If you have not the .env file in root folder, you must copy or rename the .env.example to .env

#### Application URL

.env file

```
APP_URL=http://yourdomain.tld (you must use protocol http or https)
```

#### Language

Options: en | zh | zh_cn | ru | de | es | pt | it | id | fr | hu

.env file

```
APP_LANG=en
```
Can you help us translate a few phrases into different languages? See: https://github.com/renatomarinho/laravel-gitscrum/tree/feature/language-pack/resources/lang


#### Database

.env file

```

DB_CONNECTION=mysql
DB_HOST=XXXXXX
DB_PORT=3306
DB_DATABASE=XXXXX
DB_USERNAME=XXXX
DB_PASSWORD=XXXXX
```

**Remember**: Create the database for GitScrum before run artisan command.

```
php artisan migrate --seed
```

#### Github

You must create a new Github App, visit [GitHub's New OAuth Application page](https://github.com/settings/applications/new), fill out the form, and grab your Client ID and Secret.

```
Application name: gitscrum
Homepage URL: URL (Same as APP_URL at .env)
Application description: gitscrum
Authorization callback URL: http://{URL is the SAME APP_URL}/auth/provider/github/callback
```

.env file

```
GITHUB_CLIENT_ID=XXXXX
GITHUB_CLIENT_SECRET=XXXXXXXXXXXXXXXXXX
```

#### Gitlab

You must create a new Gitlab App, visit [Gitlab new application](https://gitlab.com/profile/applications), fill out the form, and grab your Application ID and Secret.

```
name: gitscrum
Redirect URI: http://{URL is the SAME APP_URL}/auth/provider/gitlab/callback
Scopes: api and read_user
```

.env file

```
GITLAB_KEY=XXXXX -> Application Id
GITLAB_SECRET=XXXXXXXXXXXXXXXXXX
GITLAB_INSTANCE_URI=https://gitlab.com/
```

#### Proxy

.env file

```
PROXY_PORT=
PROXY_METHOD=
PROXY_SERVER=
PROXY_USER=
PROXY_PASS=
```


## Screens

![Screenshot 0](http://i.imgur.com/jejT8hY.png)
![Screenshot 0](http://i.imgur.com/apcFdv0.png)
![Screenshot 0](http://i.imgur.com/TRzRIpU.png)
![Screenshot 0](http://i.imgur.com/VcpRaNk.png)
![Screenshot 0](http://i.imgur.com/8uMYCLv.png)
![Screenshot 0](http://i.imgur.com/rIwkn7i.png)
![Screenshot 0](http://i.imgur.com/D954dbU.png)

<br>

## Database schema 

![Screenshot 1](http://i.imgur.com/zdrEkkf.png)

<br>

## Questions and issues

The [github issue tracker](https://github.com/renatomarinho/laravel-gitscrum/issues) is **_only_** for bug reports and feature requests. Anything else, such as questions for help in using the Laravel Gitscrum, should be posted in [StackOverflow](http://stackoverflow.com/questions/tagged/gitscrum) under tag `gitscrum`.

### Do you need help?

Renato Marinho: [Facebook](https://www.facebook.com/renato.marinho) / [LinkedIn](https://pt.linkedin.com/in/renatomarinho13) / Skype: renatomarinho13


## Contributing

Contributions are always welcome! https://github.com/renatomarinho/laravel-gitscrum/graphs/contributors


## License

Laravel GitScrum is licensed under the [MIT license](https://opensource.org/licenses/MIT).


## Thanks

#### Translate Team : [@orionlu0916](https://github.com/orionlu0916) , [@Bebbolus](https://github.com/Bebbolus) , [@dongm2ez](https://github.com/dongm2ez), [@rizalio](https://github.com/rizalio), [@ddmler](https://github.com/ddmler), [@Assada](https://github.com/Assada), [@edbizarro](https://github.com/edbizarro), [@ngabor84](https://github.com/ngabor84) and Manuel Ortega

- [Laravel PHP Framework](https://github.com/laravel/laravel)

- [Chart.js](https://github.com/chartjs/Chart.js)

- [Date Range Picker for Bootstrap](https://github.com/dangrossman/bootstrap-daterangepicker)

### Backers

Support us with a monthly donation and help us continue our activities. [[Become a backer](https://opencollective.com/laravel-gitscrum#backer)]

<a href="https://opencollective.com/laravel-gitscrum/backer/0/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/0/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/1/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/1/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/2/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/2/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/3/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/3/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/4/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/4/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/5/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/5/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/6/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/6/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/7/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/7/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/8/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/8/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/9/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/9/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/10/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/10/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/11/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/11/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/12/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/12/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/13/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/13/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/14/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/14/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/15/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/15/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/16/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/16/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/17/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/17/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/18/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/18/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/19/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/19/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/20/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/20/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/21/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/21/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/22/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/22/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/23/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/23/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/24/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/24/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/25/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/25/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/26/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/26/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/27/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/27/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/28/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/28/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/backer/29/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/backer/29/avatar.svg"></a>

### Sponsors

Become a sponsor and get your logo on our README on Github with a link to your site. [[Become a sponsor](https://opencollective.com/laravel-gitscrum#sponsor)]

<a href="https://opencollective.com/laravel-gitscrum/sponsor/0/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/1/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/2/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/3/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/4/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/5/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/6/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/7/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/8/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/9/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/9/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/10/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/10/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/11/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/11/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/12/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/12/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/13/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/13/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/14/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/14/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/15/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/15/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/16/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/16/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/17/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/17/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/18/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/18/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/19/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/19/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/20/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/20/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/21/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/21/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/22/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/22/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/23/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/23/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/24/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/24/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/25/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/25/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/26/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/26/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/27/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/27/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/28/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/28/avatar.svg"></a>
<a href="https://opencollective.com/laravel-gitscrum/sponsor/29/website" target="_blank"><img src="https://opencollective.com/laravel-gitscrum/sponsor/29/avatar.svg"></a>
