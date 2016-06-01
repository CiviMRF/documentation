# CMRF Project

This project aims at providing an infrastructure for the data exchange between a public facing website with a CiviCRM system. 

There is a lot of options available to integrate CiviCRM when runnin on the *same* server (e.g. Drupal Webforms integration), but we believe that in many cases CiviCRM shouldn't be run on a publicly accessible webserver - there are some serious concerns about data protection.

The CRMF project set out facilitate the setup of an interactive, individual *and* secure interaction with your constituents using CiviCRM.

The project was started in May 2016 by Erik Hommels and Björn Endres.

## Why "CiviMcRestFace"?

The catchy name is based on the [Boaty McBoatface incident](http://www.theguardian.com/environment/2016/apr/17/boaty-mcboatface-wins-poll-to-name-polar-research-vessel), and it reflects the ideas of public participation and naming issues. At the same time it contains the important key words of the project: **Civi**CRM connection to a public **fac**ing website via its **REST** API.

This is a ***working title***, and we're happy for any suggestions - ideally with the same acronym (CMRF).

## Scenario

The following depicts a typical setup:
![Basic scenario](images/scenario.png =600x)


## Structure

The heart of the project is the ``CMRF_Core``, where the basic infrastructure is implemented. Since the core has to be tightly ingrated into the host system (e.g. Drupal7, Drupal8, Wordpress, Joomla, etc.) the class is abstract and needs to be extended in order to be functional.

Linking individual functions or features of the host system (e.g. Webforms, payment systems, etc.) to the core is the the job of the ``CMRF_Connector`` projects. They register with a local core and ultimately connect CiviCRM with the host system, and *translate* between the two.

Here's a class diagram draft:
![Basic scenario](images/classes.png =600x)

