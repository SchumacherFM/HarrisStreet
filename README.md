Zookal HarrisStreet for Magento
===============================

Composer based Magento installer.

### @todos

- create a flag to remove unnecessary files like RELEASE_NOTES, license [depending on the target]
- create two flags for removing downloader and/or compiler folders/files [depending on the target]
- show a hint for which target and which DVCS branch we're currently building
- if build is for !development then create a confirm question to proceed this build. include also a json flag to switch off this confirmation
- try to separate between Magento frontend and backend. the frontend version has a complete stripped off backend. [magerun-addons uninstall-a-module](https://github.com/kalenjordan/magerun-addons#uninstall-a-module)
- try to build for target: production-be or production-fe or staging-jenkins
- create option either to move htdocs to xxxx-data dir or remove folder
- preRunCheck() add checks for required php modules like PDO ...
- if a module is `<active>false</active>` in the config xml then remove it completely ... but with care, maybe devs need some classes so we would have an
option to either remove or keep the files.
- integrate the target.json into the composer file and let the user choose for which target he/she wants to build, extend composer.
- this readme!!!
- refactor code

### Description

This software is pre-alpha but it is used in production for Zookals website.

Composer's script handler to install, update and maintain Magento (>=1.6).

Configuration of Harris Street will be read from your root composer.json file.

Uses the composer hooks:  post-install-cmd and pre-install-cmd

Example json [https://github.com/zookal/magento/blob/master/composer.json](https://github.com/zookal/magento/blob/master/composer.json)


### Config Values depending on the environment

- web/cookie/cookie_*
- dev/template/allow_symlink
- each %url% path
- netsuite credentials
- zendesk credentials

### How to magento-composer-installer

For dev env the checkout strategy is symlink while on staging and production the checkout strategy is copy and allow symlinks will be set to false.

### How to use

Add to your project-based composer.json: Please see the demo composer.json file.


Installation
------------

Require this installer in your `composer.json` file:

	"require": {
		…
        "zookal/harris-street": "dev-master",
        …
    }

Running tests
-------------
Tests must run in process isolation due to instance mocking of Mockery.

	$ git clone …
	$ composer install
	$ phpunit --process-isolation

License
-------

[Open Software License (OSL 3.0)](http://opensource.org/licenses/osl-3.0.php)


Author
------

Cyrill at Schumacher dot fm or cyrill at zookal dot com

[My pgp public key](http://www.schumacher.fm/cyrill.asc) / on [keybase.io](https://keybase.io/cyrill)

[@SchumacherFM](https://github.com/SchumacherFM)