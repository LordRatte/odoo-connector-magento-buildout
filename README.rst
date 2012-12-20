Bootstrapping the buildout
--------------------------

Bootstrapping the buildout consists in creating the basic structure of the buildout, and installing buildout itself in the directory.

The easiest and recommended way to bootstrap is to use a ``bootstrap.py`` script::

  $ wget https://raw.github.com/buildout/buildout/master/bootstrap/bootstrap.py
  $ python bootstrap.py

As an alternative and more complicated solution, you may also bootstrap by
creating a virtualenv, installing zc.buildout, then run the bootstrap::

  $ virtualenv sandbox
  $ sandbox/bin/pip install zc.buildout
  $ sandbox/bin/buildout bootstrap

Running the build

Just run ::
  $ bin/buildout


Starting OpenERP
----------------

Just run::
  $ bin/start_openerp

Or in gunicorn mode::
  $ bin/gunicorn_openerp

Using Supervisord
-----------------

To launch supervisor::
  $ bin/supervisord

This will launch automatically the process ``gunicorn_openerp``
In addition, the process ``openerp`` to launch a server in standalone
will be available in supervisor.

To manage the processes::
  $ bin/supervisorctl

In supervisorctl type ``help`` to see all commands.

Is you want autostart for ``openerp`` instead of ``gunicorn_openerp``
edit supervisor:programs in ``buildout.cfg``.
