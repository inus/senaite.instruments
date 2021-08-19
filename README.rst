*Instrument results import and export add-on for SENAITE*
=========================================================

.. image:: https://img.shields.io/github/issues-pr/senaite/senaite.instruments.svg?style=flat-square
   :target: https://github.com/senaite/senaite.instruments/pulls

.. image:: https://img.shields.io/github/issues/senaite/senaite.instruments.svg?style=flat-square
   :target: https://github.com/senaite/senaite.instruments/issues

.. image:: https://img.shields.io/badge/README-GitHub-blue.svg?style=flat-square
   :target: https://github.com/senaite/senaite.instruments#readme


Introduction
============

WARNING: This addon is not yet production ready and has not been released on PYPI


SENAITE INSTRUMENTS adds **instrument results import and export** capabilities to `SENAITE LIMS <https://www.senaite.com>`_.


Installation
============

Please follow the installations instructions for `Plone 5`_ and
`senaite.lims`_.

To install SENAITE INSTRUMENTS, you have to add `senaite.instruments` into the `eggs`
list inside the `[buildout]` section of your `buildout.cfg`::

   [buildout]
      index = https://pypi.org/simple/

   extends = https://dist.plone.org/release/5.2-latest/versions.cfg
   find-links =
       https://dist.plone.org/release/5.2-latest/
       https://dist.plone.org/thirdparty/

   # buildout.sanitycheck makes sure you're not running buildout
   # as root.
   extensions =
       buildout.sanitycheck
       mr.developer

   sources = sources
   auto-checkout = *
   #
   package-name = senaite.lims


   extends =
       base.cfg
       https://dist.plone.org/release/5.2.4/versions.cfg

   
#Added by LungaB for queue   
queue-user-name=queue_consumer
queue-user-password=queue_consumer_password

       
   parts =
       zeoserver
       client1
       client2
       backup
       queue_consumer
       queue_server
       zopescripts
       zopepy
       unifiedinstaller
    
       
   
   eggs =
    Plone[archetypes]
    plone.app.contenttypes[atrefs]
    Products.PrintingMailHost
    senaite.core
    senaite.app.listing
    senaite.app.spotlight
    senaite.app.supermodel
    senaite.impress
    senaite.jsonapi
    senaite.lims
    senaite.instruments

   [sources]
   senaite.core = git git://github.com/senaite/senaite.core.git pushurl=git@github.com:senaite/senaite.core.git branch=2.x
   senaite.app.listing = git git://github.com/senaite/senaite.app.listing.git pushurl=git@github.com:senaite/senaite.app.listing.git branch=2.x
   senaite.app.spotlight = git git://github.com/senaite/senaite.app.spotlight.git pushurl=git@github.com:senaite/senaite.app.spotlight.git branch=2.x
   senaite.app.supermodel = git git://github.com/senaite/senaite.app.supermodel.git pushurl=git@github.com:senaite/senaite.app.supermodel.git branch=2.x
   senaite.impress = git git://github.com/senaite/senaite.impress.git pushurl=git@github.com:senaite/senaite.impress.git branch=2.x
   senaite.jsonapi = git git://github.com/senaite/senaite.jsonapi.git pushurl=git@github.com:senaite/senaite.jsonapi.git branch=2.x
   senaite.lims = git git://github.com/senaite/senaite.lims.git pushurl=git@github.com:senaite/senaite.lims.git branch=2.x

   senaite.instruments = git https://github.com/rockfruit/senaite.instruments.git

   bika.coa = git git://github.com/bikalims/bika.coa.git pushurl=git@github.com:bikalims/bika.coa.git branch=2.x
   bika.ui = git git://github.com/bikalims/bika.ui.git pushurl=git@github.com:bikalims/bika.ui.git branch=2.x
   senaite.queue = git git://github.com/bikalims/senaite.queue.git


   [versions]
   # other pins not in plone
   senaite.lims = 2.0.0rc3
   senaite.impress = 2.0.0rc3
   senaite.jsonapi = 2.0.0rc2
   senaite.core = 2.0.0rc3
   senaite.lims = 2.0.0rc3
   senaite.app.supermodel = 2.0.0rc3
   senaite.app.spotlight = 2.0.0rc3
   senaite.app.listing = 2.0.0rc3
   plone.recipe.unifiedinstaller = 5.2b1
   buildout.sanitycheck = 1.0.2
   collective.recipe.backup = 4.1.0
   zc.buildout =
   setuptools =
   Pillow = 5.1.0
   cssselect2 = 0.2.2
   soupsieve = 1.9.5
   Werkzeug = 1.0.1


**Note**

The above example works for the buildout created by the unified
installer. If you however have a custom buildout you might need to add
the egg to the `eggs` list in the `[instance]` section rather than
adding it in the `[buildout]` section.


Activate the Add-on
-------------------

Please browse to the *Add-ons* Controlpanel and activate the **SENAITE INSTRUMENTS** Add-on:

.. image:: static/activate_addon.png
    :alt: Activate SENAITE INSTRUMENTS Add-on

