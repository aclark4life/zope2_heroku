
Zope2 on Heroku
===============

- Use pip-installed packages in buildout via ``include-site-packages = true``

- Store Data.fs in git, to work around no persistent file storage

Known issues
------------

- A dep fetch may timeout during push e.g. https://gist.github.com/3129617. If so, just push again.

- All deps must be listed in requirements.txt else zc.buildout will try to fetch during app start, and the build may fail due to: ``Error R10 (Boot timeout) -> Web process failed to bind to $PORT within 60 seconds of launch.``

- Even with all the deps listed, the app may occasionally fail to start due to: ``Error R10 (Boot timeout) -> Web process failed to bind to $PORT within 60 seconds of launch.`` Usually a ``heroku restart`` fixes this.
