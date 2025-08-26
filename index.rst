#####################################
First alerts end-to-end demonstration
#####################################

.. abstract::

   A roadmap for the end-to-end science demonstration of the LSST alert distribution and follow-up ecosystem, to be executed with the first alerts as part of the early science program.

Introduction
============

This is a living document that will evolve as the plans for the alert end-to-end demo evolves.

Goals
=====

To test and demonstrate the functionality and science-readiness of individual components of the alert follow-up ecosystem with LSST data, to both the science community and the general public.


Timeline
========



Prerequisites
-------------

The conditions under which the first alerts end-to-end demo can occur are:

 * agency security review complete
 * all components are online
 * targets are scheduled for observations
 * draft announcements are prepared
 * humans are available


Components
==========

Brief descriptions and links to documentation for each of the components incorporated into the first alerts end-to-end demo.


Rubin DIA and AP
----------------

DIA: Difference Image Analysis

AP: Alert Production

`LSST Science Pipelines documentation <https://pipelines.lsst.io/>`_

DIA refers to the process of image subtraction and difference-image source detection.
AP refers to the production and distribution of alert packets for difference-image sources.
This software is run by Rubin Data Management as part of Prompt Processing.


ANTARES
-------

ANTARES: Arizona–NOIRLab Temporal Analysis and Response to Events System

`ANTARES broker <https://antares.noirlab.edu/>`_

ANTARES is a full-service, real-time broker that adds contextual value to ingested alerts from multiwavelength astronomical catalogs.
Users can write their own filters to identify specific classes of objects, create watch lists for direct notification, or develop catalogs for large-scale comparisons. 
Users can interact with the system via a web portal, API, or substreams of alerts from filters.


GOATS
-----

GOATS: Gemini Observation and Analysis of Targets System

`GOATS documentation <https://goats.readthedocs.io/en/latest/>`_

GOATS is a browser-based user interface providing end-to-end automation of the entire time-domain/multi-messenger astronomy follow-up process, including target selection, triggering follow-up observations, and data reduction and analysis.
It was built using the `TOM Toolkit <https://tom-toolkit.readthedocs.io/en/stable/>`_.


AEON
----

AEON: Astronomical Event Observatory Network

`AEON documentation <https://aeonplus.github.io/>`_

AEON provides rapid, flexible, programmable access to multi-wavelength telescope facilities such as SOAR and Gemini.
Alert brokers and Target Observation Managers (TOMs) can submit follow-up observations in real-time without human intervention with AEON.


Hermes
------

`Hermes documentation <https://hermes.lco.global/about>`_

HERMES is a Message Exchange Service for Multi-Messenger Astronomy applications that allow users to both send and review messages related to a variety of events and targets of interest as well as understand opportunities for follow-up.



Science use-cases and targets
=============================