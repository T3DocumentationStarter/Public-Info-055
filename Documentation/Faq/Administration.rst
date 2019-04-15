.. include:: ../Includes.txt

.. _faq_administration:

==================
FAQ Administration
==================

Upgrade
=======

**Q**: Can I upgrade an existing site to use the latest TYPO3 version with "Pizpalue"?

**A**: Usually the object is to maintain the page tree and the content elements when upgrading. The distribution
imports a default page tree when being installed the first time. In case this isn't desired the file
:file:`typo3conf/ext/pizpalue/Initialisation/data.xml` as well as the folder
:file:`typo3conf/ext/pizpalue/Initialisation/data.xml.files` need to be deleted prior installing the distribution
for the first time.

To do so follow these steps:

#. Uninstall all extensions
#. Upgrade TYPO3
#. Download the zipped version from Pizpalue from Github
#. Delete the file :file:`../Initialisation/data.xml` as well as the folder
:file:`../Initialisation/data.xml.files`
#. Install the extension