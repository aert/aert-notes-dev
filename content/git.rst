:mod:`Git`
**********

.. module:: Git
   :synopis: Using Git

.. index:: Git

My Aliases
==========

::

    [alias]
        lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
        co = commit -a


Get Total Commits Number in git
===============================
    
::

    $ git rev-list --all | wc-l


