Git
***

.. module:: Git
   :synopsis: Using Git

.. index:: Git

My Aliases
==========

::

    [alias]
        lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
        co = commit -a

Contributing
============

See :ref:`Contributing <git-contributing>`

Get Total Commits Number in git
===============================
    
::

    $ git rev-list --all | wc-l


