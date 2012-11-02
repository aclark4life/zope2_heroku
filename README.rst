.. image:: https://raw.github.com/aclark4life/zope2-heroku/master/screenshot.png

Zope2 on Heroku
===============

- Use pip-installed packages in buildout via ``include-site-packages = true``.

- Store Data.fs in git, to work around the lack of a persistent file storage.

Known issues
------------

Keep in mind on Heroku there are two distinct phases to an application launch: git push, and application start. Dependencies are, and must be, fetched during the push phase. If we try to run buildout for anything other than creating scripts, the application will not start within 60 seconds and the launch will fail.

- A dependency fetch may timeout during push. If so, just push again.

- Even with all the dependencies listed, the application may occasionally fail to start. A ``heroku restart`` usually fixes this.
