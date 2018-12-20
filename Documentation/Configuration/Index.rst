.. include:: ../Includes.txt


.. _configuration:

=============
Configuration
=============


.. _config_installtool:

Install tool
============

Consider to review the below mentioned entries in the installtool.

.. code-block:: php

   $GLOBALS['TYPO3_CONF_VARS']['SYS']['ddmmyy'] = 'd.m.y';
   $GLOBALS['TYPO3_CONF_VARS']['SYS']['hhmm'] = 'H:i';
   $GLOBALS['TYPO3_CONF_VARS']['SYS']['phpTimeZone'] = 'Europe/Zurich';
   $GLOBALS['TYPO3_CONF_VARS']['SYS']['systemLocale'] = 'de_CH.utf8';
   $GLOBALS['TYPO3_CONF_VARS']['BE']['lockSSL'] = true;

.. tip::
   The above mentioned configurations might be part from the file "typo3conf/AdditionalConfiguration.php".
   A sample file is provided in the directory "typo3conf/ext/pizpalue/Resources/Private/FolderStructureTemplateFiles".


.. _config_seo:

SEO
===

In case TYPO3 version 8LTS is used the extensions realurl, dd_googlesitemap and url_forwarding might be installed.

TYPO3 version 8LTS
------------------

You might follow these steps to setup seo features:

#. Verify 404-handling. You might need to adjust configurations by help of the install tool (e.g. pageNotFound_handling).
#. Review sitemap by adding `?eID=dd_googlesitemap <https://www.pizpalue.buechler.pro/?eID=dd_googlesitemap>`__ to the domain
#. Review seo tags like title-tag and description meta-tag
#. Register domain as new property at google search console
#. Verify ownership by adding google-site-verification code to the related seo constant (see figure below)
#. Register domain in google analytics
#. Add google analytics code to the related seo constant (see figure below)

.. figure:: ../Images/Configuration/ConstantEditorSeo.jpg
   :width: 500px
   :alt: SEO related constants in "PIZPALUE CUSTOMER" category

   SEO related constants in "PIZPALUE CUSTOMER" category


.. _config_404:

404-Handling
============

The 404-handling can be configured in the install tool. An example configuration might look as following:

========================================== ===================================================
Parameter                                  Value
========================================== ===================================================
[FE][pageNotFound_handling]                REDIRECT:https://www.pizpalue.buechler.pro/404/
[FE][pageNotFound_handling_statheader]     HTTP/1.0 404 Not Found
========================================== ===================================================


.. _config_scrollanimation:

Scroll animation
================

The feature can be enabled in the constant editor (:ref:`PIZPALUE: CUSTOMER - Features <config_ScrollAnimation_ConstantEditor>`).

Since this feature is based on the dimensions from the visible area and the content element problems might come up
where the content element dimensions change upon scrolling, like it is the case with the lazy image loading feature.
This is why the images are configured to be fully preloaded when the scroll animation feature is enabled. This might be
overwritten with the following TS:

.. code-block:: typoscript

   lib.contentElement.settings.preload.images = 0


Enable scroll animation
-----------------------

To enable the scroll animation for a certain page follow these steps:

1. Create extension template for page

.. figure:: ../Images/Configuration/ScrollAnimation_ExtensionTemplate.png
   :width: 500px
   :alt: Create extension template for page

.. _config_ScrollAnimation_ConstantEditor:

2. Enable scroll animation in constant editor

.. figure:: ../Images/Configuration/ScrollAnimation_ConstantEditor.png
   :width: 500px
   :alt: Enable scroll animation in constant editor


.. _config_cookieconsent:

Cookie consent
==============

To show a cookie dialog the "Enable Cookie Consent"-parameter has to be set (available through the constant editor
under "PIZPALUE: CUSTOMER"). As well a link to a privacy policy page can be set in the cookie dialog.

Further configurations regarding the cookie dialog can be found und "PIZPALUE: CUSTOMER VARIOUS" in the constant editor.

.. note::
   For Google Analytics a control block can be embedded by using the string ###GoogleAnalyticsStatus### in a content
   element.

.. note::
   The cookie dialog is rendered with a partial. You might need to update your template by embedding

   .. code-block:: xml

      <f:render partial="Structure/CookieConsent" arguments="{_all}" />


.. _config_appIcons:

App icons
=========

In case just a simple favicon is required it can be specified in the category "PIZPALUE - CUSTOMER BASE" from the
constants editor.

To get an app icon set for all major platforms the resources might be generated at the
`"Favicon generator" <https://realfavicongenerator.net/>`__ website. The resulting resources need to be copied to the
server web directory and the header data assigned to the related field in the app icon section in the category
"PIZPALUE - CUSTOMER BASE" from the constants editor.
