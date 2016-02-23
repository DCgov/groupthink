========
orgwide
========

The orgwide package helps you install, update, and manage GitHub organization-specific command line scripts. Let's say your organization is called :code:`foo`.

Running :code:`orgwide --install foo` looks for a repository at :code:`https://github.com/foo/foo-cli`. If it finds one, it installs to the :code:`foo-cli` directory within :code:`~/.orgwide`. Like this:

::

    .orgwide
    └── foo-cli
        ├── CONTRIBUTING.md
        ├── LICENSE.md
        ├── README.md
        └── bin
            ├── help
            ├── init
            ├── scan
            ├── setup
            └── validate

It also install as :code:`foo` script to :code:`/usr/local/bin`, which allows you to invoke any of the scripts found within the :code:`foo-cli/bin` directory. So :code:`foo init` would run the :code:`init` script within :code:`foo-cli/bin`, :code:`foo help` would run the :code:`help` script in the same directory, and so on.

You can check for updates made to the remote :code:`foo-cli` repository with :code:`orgwide --update foo`. :code:`orgwide --upgrade foo` would install all updates. And :code:`orgwide --uninstall foo` removes both the :code:`foo` script in :code:`/usr/local/bin` and the :code:`foo-cli` directory in :code:`~/.orgwide`.

Finally, you can list all the organization commands you have installed to :code:`~/.orgwide` with :code:`orgwide --list`.

To sum up the subcommands:

* :code:`orgwide --install <org>` installs the scripts for :code:`<org>`
* :code:`orgwide --uninstall <org>` removes the scripts for :code:`<org>`
* :code:`orgwide --update <org>` checks for updates made to :code:`<org>`'s scripts
* :code:`orgwide --upgrade <org>` installs all updates made to :code:`<org>`'s scripts
* :code:`orgwide --list` lists all orgwide scripts you have installed for any :code:`<org>`

Requirements
==============

* Python (v. 2.7 or 3.3+)
* git
* If you're running Windows, use `Git Bash <https://git-for-windows.github.io/>`_

Installation
==============

[To be added to PyPi]