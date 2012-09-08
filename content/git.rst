Git
***

.. module:: Git
   :synopsis: Using Git

.. index:: Git

Guidelines
==========

* http://live.gnome.org/Git/Developers

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


List Branches and Tracking Info
==============================

::

    $ git branch -avv


Combine multiple commits into one
=================================

Use ``git rebase`` than interactively ``pick`` and ``squash`` ( see `here <http://feeding.cloud.geek.nz/2010/08/combining-multiple-commits-into-one.html>`)

