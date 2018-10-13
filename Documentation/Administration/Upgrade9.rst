.. include:: ../Includes.txt

.. _administration_upgrade_9:

======================
Upgrade to version 9.0
======================

Introduction
============

The goal from this distribution is to facilitate a robust foundation using as view extensions as possible. Using less 
extensions reduces the footprint and improves the upgrade experience.

With release 9 the distribution has been adapted to TYPO3 9LTS and the bootstrap_package 10. The major changes include:

`TYPO3: <https://typo3.org/article/typo3-v9-lts-youre-the-one-that-i-want/>`__

-  Speaking URLs Out of the Box 
-  Search Engine Optimization (SEO) 
-  Site Management
-  Major Backend Changes
-  System Maintenance Area
-  Conditional Variants for Form Elements
-  General Data Protection Regulation (GDPR) 

`bootstrap_package: <https://github.com/benjaminkott/bootstrap_package>`__

-  Bootstrap 4 using scss
-  Cookie consent
-  Content elements
-  Background images for content elements

As a result the distribution needed to be refactored and adapted significantly:

-  Apply latest naming conventions
-  Remove dependency to extensions realurl, dd_googlesitemap and bootstrap_gridelements
-  Switch CSS preprocessing from Less to Scss


Upgrading the distribution from earlier versions (e.g. the PP_8-6 branch) includes the following steps:

-  Prepare
-  Upgrade
-  Review


Prepare
=======


Upgrade
=======


Review
======

Cookie consent
--------------


