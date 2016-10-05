# CMRF Project

CMRF is the CiviCRM Modular Remote-Access Framework. The project aims at providing an infrastructure for the data exchange between a public facing website with a CiviCRM system. 

There is a lot of options available to integrate CiviCRM when runnin on the *same* server (e.g. Drupal Webforms integration), but we believe that in many cases CiviCRM shouldn't be run on a publicly accessible webserver - there are some serious concerns about data protection.

The CRMF project set out facilitate the setup of an interactive, individual *and* secure interaction with your constituents using CiviCRM.

The project was started in May 2016 by Erik Hommel (erik.hommel/civicoop.org) and Björn Endres (endres/systopia.de). We're happy for any kind of support.

## Why the crude acronym?

The acronym CMRF was based on the working title "Civi McRest Face" (after the [Boaty McBoatface incident](http://www.theguardian.com/environment/2016/apr/17/boaty-mcboatface-wins-poll-to-name-polar-research-vessel)) We meant to emphasise public participation, and at the same time it contained the important key words of the project: **Civi**CRM connection to a public **fac**ing website via its **REST** API.


## Scenario

The following depicts a typical setup:<br/>
<img src="images/scenario.png" width="800">


## Structure

The heart of the project is the ``CMRF_Core``, where the basic infrastructure is implemented. Since the core has to be tightly ingrated into the host system (e.g. Drupal7, Drupal8, Wordpress, Joomla, etc.) the class is abstract and needs to be extended in order to be functional.

Linking individual functions or features of the host system (e.g. Webforms, payment systems, etc.) to the core is the the job of the ``CMRF_Connector`` projects. They register with a local core and ultimately connect CiviCRM with the host system, and *translate* between the two.

Here's a class diagram draft:<br/>
<img src="images/classes.png" width="800">

