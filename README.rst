
Zope2 on Heroku
===============

- Use pip-installed packages in buildout via ``include-site-packages = true``

- Store Data.fs in git, to work around no persistent file storage

Known issues
------------

- All deps must be listed in requirements.txt else zc.buildout will try to fetch, and the build may fail due to: ``Error R10 (Boot timeout) -> Web process failed to bind to $PORT within 60 seconds of launch.``

- Even with all the deps listed, the build may occasionally fail due to: ``Error R10 (Boot timeout) -> Web process failed to bind to $PORT within 60 seconds of launch.`` Usually a ``heroku restart`` fixes this.
