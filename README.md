# Tonik

[![Build Status](https://travis-ci.org/tonik/tonik.svg?branch=master)](https://travis-ci.org/tonik/tonik)

### Tonik Starter Theme aims to modernize, organize and simplify some aspects of WordPress theme development. Take a look at what is waiting for you:

- Child theme friendly **Autoloader**
- Simple **Theme Service Container**
- Enhanced **Templates Locator** with support for passing data
- Centralized Theme Configs
- Use of PHP [Namespaces](http://php.net/manual/pl/language.namespaces.php)
- [Laravel Elixir](https://laravel.com/docs/5.3/elixir) as task runner for managing front-end assets
- **SASS** and **Bootstrap**
- JavaScript **ES6**

## Requirements

Make sure you have all these dependences installed before moving on:

- WordPress >= 4.7
- PHP >= 5.6
- [Composer](https://getcomposer.org)
- [Node.js](https://nodejs.org)

# Installation

## Creating new Theme

Create project via `composer create-project` composer command.

```bash
$ composer create-project tonik/tonik <theme-name>
```

You can also directly download or clone the repository to the `wp-content/themes` directory.

```bash
# Clone repository to the <theme-name> folder.
$ git clone git@github.com:tonik/tonik.git <theme-name>
```

## Resolving Dependences

Install back-end dependencies and generate an autoloading file.

```bash
# Install composer dependencies.
$ composer install -o
```

Install frontend dependencies and task runner.

```bash
# Install node dependencies.
$ npm install
```

# Development

## Initializing a Theme

Starter comes with simple CLI and `gin tonik:shake` command, which allows you to easily fill theme details and information like name, description and project namespace. Simply call `php gin tonik:shake` command in the theme root directory. A setup wizard will guide you through the entire process.

```bash
# Run setup wizard.
$ php gin tonik:shake
```

## Compiling Assets

Theme uses [Laravel Elixir](https://laravel.com/docs/5.3/elixir) to compile it's scripts and stylesheets.

```bash
# Run compile tasks.
$ gulp

# Watch for file changes and run compile tasks.
$ gulp watch

# Compile assets for production.
$ gulp --production
```

## Folders and Files Structure

This starter theme introduces "easy to follow" folder structure, which enforces to divide your theme logic into separate files.

```
themes                              # — Root of your theme
    ├── bootstrap/                  # — Files responsible for bootstrapping a theme
    │   ├── compatibility.php       # — Theme compatibility checker (don't edit)
    │   ├── theme.php               # — Theme bootstraper script (don't edit)
    ├── config/                     # — Configuration files
    │   ├── theme.php               # — Theme configuration file
    ├── public/                     # — Front-end compiled/builded assets (don't edit)
    ├── resources/                  # — Resources files
    │   ├── assets                  # — Front-end source assets
    │   │   ├── js                  # — Theme JavaScript files
    │   │   ├── sass                # — Theme Stylesheets files
    │   │   ├── images              # — Theme images
    │   │   ├── fonts               # — Theme fonts
    │   ├── languages               # — Theme translations
    │   ├── templates               # — Theme templates
    ├── src/                        # — Theme application logic
    │   ├── Http/                   # — Http layer of theme
    │   │   ├── ajaxes.php          # — Theme ajaxes endpoints
    │   │   ├── assets.php          # — Theme styles and scripts loading
    │   ├── Setup/                  # — Setups for theme
    │   │   ├── actions.php         # — Theme action hooks
    │   │   ├── filters.php         # — Theme filter hooks
    │   │   ├── navs.php            # — Theme navigation areas
    │   │   ├── shortcodes.php      # — Theme shortcodes
    │   │   ├── sidebars.php        # — Theme widgets areas
    │   │   ├── supports.php        # — Theme supports
    │   │   ├── thumbnails.php      # — Theme custom image sizes
    │   │   ├── widgets.php         # — Theme custom widgets
    │   ├── Structure/              # — Structures for theme
    │   │   ├── posttypes.php       # — Theme custom post types
    │   │   ├── taxonomies.php      # — Theme custom taxonomies
    │   ├── helpers.php             # — Collection of helper functions
    ├── 404.php                     # — 404 page controller
    ├── composer.json               # — PHP dependences and PSR-4 Autoloading
    ├── footer.php                  # — Footer partial template
    ├── functions.php               # — Bootstrapping the theme. Initiates Autoloader and Composer (don't edit)
    ├── gin                         # — CLI Runner (don't edit)
    ├── header.php                  # — Header partial template
    ├── index.php                   # — Index page controller
    ├── package.json                # — NPM dependencies and scripts
    ├── screenshot.png              # — Theme screenshot image
    ├── style.css                   # — Theme details information (don't write any CSS declarations in here)
```

## USAGE.md Boilerplate

[USAGE.md](https://github.com/tonik/tonik/blob/master/USAGE.md) provides "How to use" guide for themes created with this starter. Remember to properly fill this file before finalizing the project. Your clients will be grateful.